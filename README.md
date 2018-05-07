# Kaypro

## Kaypro Keyboard -> USB Interface

This project is about convering a retro Kaypro keyboard so that it can be plugged in to any computer via the USB port.

There are a lot of old Kaypro computers on eBay, and some keyboard only listings. The Keyboard uses a four wire interface and I have reverse engineered it. This project details the Kaypro keyboard comms format and also eventually will contain all the software to convert this to a USB device by interfacing it to an AVR USB-capable microcontroller.

Check the files for the interface spec in the [techincal file](kaypro_technical.md).

The USB device will use the standard HID USB keyboard class, although some fancy footwork is needed because the Kaypro keyboard doesnt send information about modifiers or key up and key down events. So these have to be inferred from the codes that it does send.

One solution would be to convert the Kaypro serial into PS/2 keyboard serial and then use a PS/2 to USB adapter. However the point of this project is for me to learn how to code for USB.




