Created: 16/09/2023 at 16:25

### General Remarks
- many different sensor types-
- some sensore require input from CPU (activate, read, deactivate)
- scope is more on interfacing than on sensor physics

### Outputs
- binary signal (0, 1) e.g. tactile sensor
- analog signal (0..5v) e.g. inclinometer
- timing signal (PWM) e.g. gyroscope
- serial link (USB) e.g. GPS Module
- parallel link e.g. Digital Camera

#### Binary Sensor
- easy to interface
- use a resistor and link to digital input of CPU
![[Sensors-1694853017297.jpeg]]

### Debouncing
#### Hardware Solution
Analog: Resistor-capacitor circuit  (left)
Digital: Flip-Flop with single-pole / double-throw switch (right)

![[Sensors-1694853159664.jpeg]]
#### Software Solution
Add a delay between accepting inputs

### Encoder
Two types, incremental encoder and absolute encoder.
![[Sensors-1695032903052.jpeg]]

Encoder signal (2 lines) are connected to microcontroller like 2 binary sensors.
Microcontrollers usually have special internal registers for *pulse counting*.

#### Incremental Encoder
- usually requires 2 sensors to determine *speed* and *direction*

##### Technology
Magnet, hall sensors (incremental)

Optical sensors with black/white segments

#### C Code
```c
void setup() {
  pinMode(ENC1, INPUT_PULLUP);
}

int ENCODERRead(int ENC) {
  static int count = 0, E, E_old = 0;

  E = digitalRead(ENC);
  if (E && !E_OLD) count ++; // rising edge
  E_old = E;

  return count;
}
```

### Digital Sensors
Usually more complex, and more accurate than analog sensors.
![[Sensors-1695033393434.jpeg]]
![[Sensors-1695033730662.jpeg]]

#### Interfacing
##### Hardware
![[Sensors-1695033761994.jpeg]]

##### Software
```c
int psd() {
  int val = 0;

  digitalWrite(SET, LOW);
  usleep(70000);

  for (int i = 0; i < 8; i++) {
    digitalWrite(SET, HIGH); usleep(200); // rising edge
    digitalWrite(SET, LOW); usleep(200); // falling edge
    val = (val << 1) | digitalRead(PSD); // shift bit left, and bitwise OR operation
  }

  return val;
}
```

### Analog Sensors and A/D Converter
![[Sensors-1695034184427.jpeg]]

#### A/D Converter
![[Sensors-1695034195617.jpeg]]

- transform analog signal into a sequence of numbers
- sampling rate and conversion number range will determine the digitizing quality
- there will always be information loss
- signal has to be provided at correct level, e.g. 0..5V

##### Parallel
![[Sensors-1695034304806.jpeg]]

##### Serially Digital
![[Sensors-1695034326855.jpeg]]

##### Serially Digital with Multiple Inputs
![[Sensors-1695034470324.jpeg]]

#### Diagrams
![[Sensors-1695034562022.jpeg]]
![[Sensors-1695034710542.jpeg]]
The right half is familiar from the digital sensor, but the left is setting the parameters.

#### Interfacing
##### Hardware
![[Sensors-1695034788064.jpeg]]

##### Software
```c
int convert(int sensor) { //range 0..7
  digitalWrite(DATA_IN, HIGH);
  digitalWrite(CLOCK, HIGH); usleep(200);
  digitalWrite(CLOCK, LOW); usleep(200);

  for (int i = 0; i < 3; i++) {
    digitalWrite(DATA_IN, sensor >> (2 - i) & 1);
    digitalWrite(CLOCK, HIGH); usleep(200);
    digitalWrite(CLOCK, LOW); usleep(200);
  }

}
```

### PWM Sensors
![[Sensors-1695042929538.jpeg]]

The data given us is the elapsed time between the rising edges of the signal. And reading that is how we get our digital value.

![[Sensors-1695043209149.jpeg]]

### Sensor Calibration
Sensor output may be linear or non-linear to measured dimension:
- data has to be calibrated
- for linear relationships a few initial measurements are enough
- non-linear measurements: complete table is required
- for simple relationships only a *formula* is need
- for arbitrary relationships a *lookup table* is required

### Digital Cameras
Interfacing to CPU
- depends on sensor chip specs
- usually a parallel interface
- many sensors proved different interfacing protocols
![[Sensors-1695044091834.jpeg]]![[Sensors-1695044105167.jpeg]]
![[Sensors-1695044131662.jpeg]]
![[Sensors-1695044165003.jpeg]]

#### Problem
- every pixel causes an interrupt
- interrupts are expensive

#### Solution
- using a RAM buffer for image and read the full image with a single interrupt
![[Sensors-1695044254210.jpeg]]

### Image Data Formats
![[Sensors-1695044300905.jpeg]]![[Sensors-1695044309475.jpeg]]
![[Sensors-1695044436952.jpeg]]
![[Sensors-1695044445032.jpeg]]![[Sensors-1695044455366.jpeg]]![[Sensors-1695044466450.jpeg]]![[Sensors-1695044471659.jpeg]]

We have lost resolution here for the colour.

#### Implementation
![[Sensors-1695044513397.jpeg]]