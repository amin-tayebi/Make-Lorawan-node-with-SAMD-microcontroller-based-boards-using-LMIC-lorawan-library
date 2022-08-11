# Make-Lorawan-node-with-SAMD-microcontroller-based-boards-using-LMIC-lorawan-library
Solution to Make a Lorawan node with all SAMD microcontroller based boards using LMIC lorawan library (such as Arduino Nano IoT 33, ...)
With this solution you are simply use arduino nano IoT and other SAMD microcontroller boards (ARM cortex family boards) in your project to gather with LMIC MCCI library project.

Description --------------------------------------------------------------------------------------------------------------------------

As  ARDUINO UNO with 32kb was not enough to put SDI12 sensor library and LMIC MCCI library to gather, but Arduino Nano IoT 33  has 256kb flash memory I used it in my project. This is an amazing solution for using LMIC library in all types of SAMD boards such as: 
ARDUINO ZERO
ARDUINO MKR 100
ARDUINO MKR ZERO
ARDUINO MKR WIFI 1010
ARDUINO MKR FOX 1200
ARDUINO MKRWAN 1300
ARDUINO MKRWAN 1301
ARDUINO MKR GSM 1400
ARDUINO MKR NB 1500
ARDUINO MKR VIDOR 4000
ADAFRUITE CIRCUIT PLATGROUND EXPRESS
ARDUINO M0 PRO
ARDUINO M)
ARDUINO TIAN

I used pinmap like you and leave other pins like arduino uno.:
const lmic_pinmap lmic_pins = {
.nss = 6, // chip select on SAMD21 mini
.rxtx = LMIC_UNUSED_PIN,
.rst = LMIC_UNUSED_PIN,
.dio = {2, 3, 4}, //DIO0, DIO1 and DIO2 connected
};

Hardware equipment -------------------------------------------------------------------------------------------------------------------------

Arduino nano IoT 33 board
Related USB cable (connect board to the PC)
Any Lorawan module (based on RFM95 radio transiver such as Lora BEE, dragino sheild,...)

Software equipment -------------------------------------------------------------------------------------------------------------------------

Arduino-IDE software

Resources -----------------------------------------------------------------------------------------------------------------------

Arduino nano 33 IoT pinout:
https://www.etechnophiles.com/arduino-nano-33-iot-pinout-spec-board-layout/

lora bee pinout:
https://it.aliexpress.com/item/32855366206.html

Downloading Lorawan LMIC MCCI catena library:
https://github.com/mcci-catena

Arduino Nano IoT 33 user-manual
https://docs.arduino.cc/resources/dat...
