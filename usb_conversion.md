## Notes about interfacing the Kaypro Keyboard to USB 2.0

*May 5, 2018*


1. Use the USB device capability of the ATMEGA32u4 microcontroller from Atmel/Microchip.
2. Use a simple 5V AVR board from Adafruit or Sparkfun, or the Arduino Micro, to talk to USB and the keyboard.
3. Connect the RX USART input to the AVR chip to the keyboard output, at 300 baud.
4. Either the TX output from the AVR chip or some other pin will drive the beeper input to the keyboard.
5. At the moment I expect to use an external 5V supply and not worry about USB current or power down modes.
6. Pretend to be a 101 key standard US layout keyboard and use the standard keyboard class of the USB HID interface.
7. Convert received Kaypro bytes to keydown plus modifier keycodes, and auto generate keyup events after a short delay.
8. I'm not quite sure if I will drive the beeper in some way.
9. Send the standard keyboard LED codes from the HID USB OUT endpoint to spare PIOs on the AVR board.
10. I'm not sure about suppoting boot mode.
11. Not all keys are present, e.g. there are no alt keys, or any function keys. There is the option 
to use the keypad keys as function keys. There is a line feed key - this could send a CRTL-J.
12. At the moment I am considering using the LUFA library to implement the USB part. 
\It takes a lot of learning but is well engineered.

