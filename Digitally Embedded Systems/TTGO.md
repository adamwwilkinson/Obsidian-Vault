Created: 25/08/2023 at 10:16

![[TTGO-1692929865294.jpeg]]

### I/O Pins
Traditional processors have a fixed number of inputs and outputs.

Modern processors have I/O lines that can be configured as inputs or outputs.

Reading input with an *external* pull-up resistor
```c
pinMode(26, INPUT); // set pin to input
x = digitalRead(26); // read data
```

Reading from an *internal* pull-up resistor
```c
pinMode(26, INPUT_PULLUP); // set pin to input
x = digitalRead(26); // read data
```

Writing output with LED at pin 27 and button at pin 26.
```c
pinMode(27, OUTPUT); // set pin to output
digitalWrite(27, HIGH); // write data (low would turn it off)
```

#### Push Button For LED
```c
#define PUSH 26
#define LED 27

void setup() // init IO
{
  pinMode(PUSH, INPUT_PULLUP);
  pinMode(LED, OUTPUT);
}

void loop() {
  digitalWrite(LED, !digitalRead(PUSH));
}
```

#### Toggle Button for LED
```c
#define PUSH 26
#define LED 27

void setup() // init IO
{
  pinMode(PUSH, INPUT_PULLUP);
  pinMode(LED, OUTPUT);
}

void loop() {
  static int previous = 0; now = 0; state = 0;

  now = !digitalRead(PUSH);
  if (now != previous) {
    state = now;
    previous = now;
  }
  digitalWrite(LED, state);
  usleep(100 * 1000); // 100ms
}

