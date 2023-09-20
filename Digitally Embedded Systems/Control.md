Created: 16/09/2023 at 14:42

### Why?
Supplying a certain voltage / pulse width will make the motor spin at a certain speed, however this only works at idle, and the motor will slow down when loaded.

### Feedback Control
Using a feedback control we can make sure a desired speed is maintained, even when the motor is loaded.

If the motor is too slow, we increase the voltage, and if it is too fast, we decrease the voltage.

#### How?
We can do this by reading the current speed of the motor, and comparing it to the desired speed.

#### Issues
- time delay of controller
- time delay of motor
- inaccuracy of encoder data
- inaccuracy of actuator movement

### On-Off Controller
Only on/off of control value
![[Control-1694846850625.jpeg]]

When actual speed is above desired we turn the motor off, and when it is below we turn it on.
![[Control-1694846972590.jpeg]]

### Encoder Reading for TTGO/ESP32
```c
void setup() {
  pinMode(ENCODER_A, INPUT_PULLUP);
  pinMode(ENCODER_B, INPUT_PULLUP);
}

void loop() {
  static int count = 0, ENC_A = 0, ENC_B = 0, ENC_A_prev = 0, ENC_B_prev = 0;

  ENC_A = digitalRead(ENCODER_A);
  ENC_B = digitalRead(ENCODER_B);

  if (ENC_A != ENC_A_prev) count ++;
  if (ENC_B != ENC_B_prev) count --;
  ENC_A_prev = ENC_A; ENC_B_prev = ENC_B;
}
```

### Quadrature Encoder
Like a car's odometer, but runs both forwards and backwards.
![[Control-1694848220582.jpeg]]

#### On-Off Code

```c
int v_des;

void onoff_controller() {
  int enc_new, r_mot;
  static int enc_old;

  enc_new = ENCODERRead(1);
  v_act = (enc_new - enc_old) * 100; // speed in encoder-ticks per second (assumin 100 calls per second)

  if (v_act < v_des) r_mot = 100;
  else r_mot = 0;

  MOTORDrive(1, r_mot);
  enc_old = enc_new;
}
```

#### Calling the Control Subroutine
```c
int main () {
  TimerHandle t1;
  t1 = OSAttachTime(10, onoff_controller);
  while (KEYRead() != KEY4) { } // do other tasks here
  OSDetachTimer(t1);
  return 0;
}
```

### Proportional Control
$R(t) = K_p \times (v_{des}(t) - v_{act}(t))$
![[Control-1694848672903.jpeg]]
![[Control-1694849193061.jpeg]]

#### Code in C
```c
int v_des;

void onoff_controller() {
  int enc_new, r_mot;
  static int enc_old;

  enc_new = ENCODERRead(1);
  v_act = (enc_new - enc_old) * 100; // speed in encoder-ticks per second (assumin 100 calls per second)

  e_func = v_des - v_act;
  r_mot = K_p * e_func;

  r_mot = min(r_mot, +100);
  r_mot = max(r_mot, 0);

  MOTORDrive(1, r_mot);
  enc_old = enc_new;
}
```

### Integral Controller
Problem: The P-Controller may reach an equilibrium without reaching the target velocity, this is called **steady-state error**.

Solution: Add an integral part to eliminate the steady-state error, $R(t) = K_p \times [e(t) + \frac{1}{T_i} \int_0^t e(\tau) d\tau]$
![[Control-1694849533015.jpeg]]

$$R_n = K_p \times e_n + Q_I \times t_{\delta} \times \sum_{i=0}^n (e_i + e_{i + 1})/2$$
$$R_{n - 1} = K_p \times e_{n - 1} + Q_I \times t_{\delta} \times \sum_{i=0}^{n - 1} (e_i + e_{i + 1})/2$$

$$R_n - R_{n-1} = K_p \times (e_n - e_{n - 1}) + Q_I \times t_{\delta} \times (e_n + e_{n - 1})/2$$

$$R_n = R_{n - 1} + K_p \times (e_n - e_{n - 1}) + K_I \times (e_n + e_{n - 1})/2$$

```c
int v_des;

void onoff_controller() {
  int enc_new, r_mot;
  static int enc_old;

  enc_new = ENCODERRead(1);
  v_act = (enc_new - enc_old) * 100; // speed in encoder-ticks per second (assumin 100 calls per second)

  static_int r_old = 0; e_old = 0;

  e_func = v_des - v_act;
  r_mot = r_old + Kp*(e_func - e_old) + Ki*(e_func + e_old)/2;

  r_old = r_mot; e_old = e_func;

  r_mot = min(r_mot, +100);
  r_mot = max(r_mot, 0);


  MOTORDrive(1, r_mot);
  enc_old = enc_new;
}
```

### Deriviative Controller
Problem: P-Controller responds slow to a change in input, P-Controller with high gain tends to oscillate

Solution: Add a derivative part to increase the response speed, $R(t) = K_p \times [e(t) + \frac{1}{T_i} \int_0^t e(\tau) d\tau + T_d \frac{de(t)}{dt}]$

$$R_n = R_{n - 1} + K_p \times (e_n - e_{n - 1}) + K_I \times (e_n + e_{n - 1})/2 + K_D \times (e_n - 2e_{n - 1} + e_{n - 2})$$

```c
int v_des;

void onoff_controller() {
  int enc_new, r_mot;
  static int enc_old;

  enc_new = ENCODERRead(1);
  v_act = (enc_new - enc_old) * 100; // speed in encoder-ticks per second (assumin 100 calls per second)

  static_int r_old = 0; e_old = 0; e_old2 = 0;

  e_func = v_des - v_act;
  r_mot = r_old + Kp*(e_func - e_old) + Ki*(e_func + e_old)/2 + Kd*(e_func - 2*e_old + e_old2);


  r_mot = min(r_mot, +100);
  r_mot = max(r_mot, 0);

  e_old2 = e_old;
  r_old = r_mot; e_old = e_func;

  MOTORDrive(1, r_mot);
  enc_old = enc_new;
}

```
![[Control-1694851554557.jpeg]]

### PID Controller
A combination of P, I, and D controller.
- simple, universal controller
- trade-offs: response time vs stability
- noise limits max proportional gain

### PID Parameter Tuning
#### Manual Tuning
1. Select typical operating setting for desired speed, turn off integral and derivite part turn off integral and derivative part, then increase $K_P$ to max or until oscillation occurs
2. If system oscialltes divide $K_P$ by 2
3. Increase $K_D$ and observe behaviour when changing desired speed by about $5\%$. Choose a value of $K_D$ that gives a fast response without oscillation
4. Slowly increase $K_I$ until oscillation starts, then divide $K_I$ by 2.5

### Velocity Control and Position Control
Velocity control is where we can meet and maintain a speed.

Position control also incorporates a start/stop phase and makes the motor stop at a certain location.

#### Practical Way of achieving Position Control
- use velocity control in start phase and continous phase
- monitor current position and calculate begin of end phase
- continously update speed while decelerating
![[Control-1694852297584.jpeg]]

### Driving a Vehicle
![[Control-1694852427913.jpeg]]

#### Straight Line
Driving in a straight line becomes difficult.

Using two PID controllers to the left and right motor, we can control the speed of each motor individually. By inserting a Integrator controller between the two PID controllers, we can make sure the vehicle motors matches in speed.

![[Control-1694852605089.jpeg]]

#### Turning
![[Control-1694852634118.jpeg]]
