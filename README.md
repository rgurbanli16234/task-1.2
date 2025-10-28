# task-1.2
The code operates the LED using lower-level hardware registers with no dependence on Arduino functionalities. When DDRB |= (1 << 5) instruction is executed, bit 5 of the DDRB register is set to 1, forming pin PB5 (Arduino pin 13) as an output pin.

In the loop, when instruction is executed, PORTB |= (1 << 5) sets bit 5 of PORTB to 1. Thus, 5 volts is sent to the LED, and LED is turned on. There is 0 volts when LED is turned off, as instruction PORTB &= ~(1 << 5) clears the same bit to 0. The delays work the same as before.

This is faster as it is talking directly to the hardware without any steps in-between. Arduino functions have to figure out which register and bit corresponds to pin 13, but we already know it's bit 5 of PORTB.

Program Start
    ↓
Setup: DDRB bit5 = 1 (Output mode)
    ↓
Loop Begin
    ↓
Set PORTB bit5 = 1 → LED ON
    ↓
Delay 500ms
    ↓
Set PORTB bit5 = 0 → LED OFF
    ↓
Delay 500ms
    ↓
Repeat
