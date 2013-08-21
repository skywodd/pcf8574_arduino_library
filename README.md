# PCF8574 Arduino library
## By SkyWodd

### Overview
---

The "PCF8574" chip is an I2C I/O expander that free some of your Arduino pins by controlling them over I2C.
The PCF8574 is directly powered by the 5v rail of your arduino and let you control 8 I/O with only two common wires (I2C bus) !

Remarks: the PCF8575 is the same chip as the PCF8574 but with 16 I/O instead of 8.
A special variant of this library for PCF8575 is also available.


## Library API
---

This library has the same API as the standard Arduino GPIO API (digitalRead, digitalWrite, ...).

This library also support interrupts on any of the PCF8574 pins.
To do this the library internaly use the "Pin Change Interrupt (PCINT)" capability of AVR microcontrolers.
By this way any pins of your Arduino can be used to wire the "INT" pin of the PCF8574.

Remarks: the interrupt "check and process" routine of the library is public and require the user to provide an "global scope" wrapping fonction to work.
This is do in order to allow multiple PCF8574 to use the same interrupt pin ("INT" pin) on the Arduino board with call to multiple PCF8574 class instances.