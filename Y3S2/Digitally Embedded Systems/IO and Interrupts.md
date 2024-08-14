Created: 05/10/2023 at 16:27

### Device Drivers
A number of IO routines for a particular device is grouped as a device driver.
Each driver should comprise commands for initialization, closing, testing, and fuctions.

### Device Input
A data transfer can be
1. CPU initiated (polling)
2. Device initiated (interrupt)

Polling we have looked at before, but interrupts are new.

### Interrupts
![[IO and Interrupts-1696494845733.jpeg]]

Controllers have several interrupt lines with different priorities.

#### Example Count Pulses
```c
#define BUTTON_L 0
#include <TFT_eSPI.h>
TFT_eSPI tft = TFT_eSPI();
int count = 0;

void setup() {
  pinMode(BUTTON_L, INPUT_PULLUP);
  attachInterrupt(digitalPinToInterrupt(BUTTON_L), countPulses, FALLING);
}

void countPulses() {
  count++;
}
```

#### Timer
![[IO and Interrupts-1696495319587.jpeg]]

#### Watchdog Timer
Useful to see if the program is still running.
![[IO and Interrupts-1696495553858.jpeg]]

### Parallel Or Serial Transmission
Parallel: 8 bit concurrently -> parallel
On a microcontroller, digital I/O lines

Serial: 8 bits consecutively -> serial
On a microcontroller, 2 digital I/O lines

#### Parallel Transmission
- bi directional
- half-duplex (either send or recieve but not either)
- send 8 data bits concurrently
- requires additional control lines
- can only be used for short distances (1 - 2m)
![[IO and Interrupts-1696496229874.jpeg]]
##### Printer Handshake
![[IO and Interrupts-1696496372461.jpeg]]
![[IO and Interrupts-1696496461489.jpeg]]

##### Checksum
Checksum needed to ensure transmission is correct. Calculated by getting the sum of the transmitted bytes MOD 256.
![[IO and Interrupts-1696498546863.jpeg]]

#### Serial Transmission
- bi directional
- full-duplex (can send and recieve at the same time)
- send single bit at a time
- only 3 hours

##### Serial Connections
RS232C: standard (slow) serial connection
RS422: fast serial connection using differential data lines
USB: high speed serial connection
![[IO and Interrupts-1696501803911.jpeg]]

##### Transmission
Order:
1. start bit
2. data 7 or 8 bit, least significant bit first
3. parity bit (odd or even) for error detection
4. stop bit (1 or 2)
5. idle line (high)

###### Rate
Measures in bits per second, in binary signaling, the baud rate is the same as the bit rate.
Where baud rate measures symbols per second.

##### Parity
For Odd parity, count the number of 1s in the data bits and add a 1 if the number is even else append a 0. This means the sequence of (9) bits should always have an odd number of 1s.
![[IO and Interrupts-1696502187317.jpeg]]![[IO and Interrupts-1696502395050.jpeg]]