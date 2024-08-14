Created: 26/08/2023 at 16:53

Built in many different ways, electrical motors, pnuematic, hydraulic, etc.

### Motor and Encoder
![[Actuators-1693040172842.jpeg]]

A single encoder will just notice everytime the whhel has turned a full rotation, but we can use two encoders to notice the direction of the wheel.


Motor speed is determined by supplied voltage, and the motor direction is determined by the polarity of the voltage.

Cannot generate an analog power signal (1A to 10A) directly from microcontroller, use of an external amplifier is needed. (Too much current being drawn)

Gears on the motor shaft increases the encoder accuracy. Putting the encoder before the gear box will increase the accuracy of the encoder.

### H-Bridge
Allows us to control the direction of the motor.
![[Actuators-1693040789308.jpeg]]

Drive forward, close S1 and S2, open S3 and S4.
Drive backward, close S3 and S4, open S1 and S2.

Hardware implementation using relays:
![[Actuators-1693040887921.jpeg]]

### Power Amplifier
![[Actuators-1693041007424.jpeg]]
![[Actuators-1693041079200.jpeg]]

### Speed Control
![[Actuators-1693041244950.jpeg]]
![[Actuators-1693041380525.jpeg]]

The larger the pulse-width, the faster the motor will go.

### Servos
Instead of encoding to a certain speed, servos encode to a certain position. Typically used in model airplanes. Servos require a PWM (pulse width modulation) signal of 50Hz.

Pulse should be between 0.5 ms and 2.0 ms long (extreme left or right).
![[Actuators-1693041766124.jpeg]]

### Stepper Motors
Incrementally dirven motors, used in printers, scanners, etc.

Characterised by:
- number of steps per revolution
- max number of steps per second

Works with 2 independent coils on the motorshaft, one coil to turn the motor, and the other to hold it in place.
![[Actuators-1693041926376.jpeg]]