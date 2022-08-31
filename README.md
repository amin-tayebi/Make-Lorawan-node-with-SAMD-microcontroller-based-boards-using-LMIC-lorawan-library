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

Pinmap used:
const lmic_pinmap lmic_pins = {
.nss = 6, // chip select on SAMD21 mini
.rxtx = LMIC_UNUSED_PIN,
.rst = LMIC_UNUSED_PIN,
.dio = {2, 3, LMIC_UNUSED_PIN}, //DIO0, DIO1 and DIO2 connected
};

Hardware equipment -------------------------------------------------------------------------------------------------------------------------

Arduino nano IoT 33 board
Related USB cable (connect board to the PC)
Any Lorawan module (based on RFM95 radio transiver such as Lora BEE, dragino sheild,...)

Software equipment -------------------------------------------------------------------------------------------------------------------------

Arduino-IDE software

Important Notes -------------------------------------------------------------------------------------------------------------------------

1) In CATENA_MCCI_LMIC_Lorawan and IBM_MCCI_LMIC_Lorawan libraries in ABP mode without change PIN it works as we put in my Github page (https://github.com/amin-tayebi):
    .nss = 6,
    .rxtx = LMIC_UNUSED_PIN,
    .rst = 5,
    .dio = {2, 3, 4},  

2) In CATENA_MCCI_LMIC_Lorawan library in ABP mode in order to avoid crash you can also enable link check validation at this line:
    LMIC_setLinkCheckMode(1);

3) You can add below code because if LMIC OTAA sketch (even with Arduino uno) stop running after 1 to 30 minutes and you saw error:
../Documents/Arduino/libraries/MCCI_LoRaWAN_LMIC_library/src/lmic/radio.c:1065


The value 0.5 has been empirical chosen. It is possble also trying:
1, 2, 3, 4, 5, 0.9, 0.8, 0.7, 0.6

By adding this code above the line "do_send(&sendjob);" problem will be solved.

// Let LMIC compensate for +/- 0.5% clock error
LMIC_setClockError(MAX_CLOCK_ERROR * 0.5 / 100);
 
Resources -----------------------------------------------------------------------------------------------------------------------

Arduino nano 33 IoT pinout:
https://www.etechnophiles.com/arduino-nano-33-iot-pinout-spec-board-layout/

lora bee pinout:
https://it.aliexpress.com/item/32855366206.html

Downloading Lorawan LMIC MCCI catena library:
https://github.com/mcci-catena

Arduino Nano IoT 33 user-manual
https://docs.arduino.cc/resources/dat...
