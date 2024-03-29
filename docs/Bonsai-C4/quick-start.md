# Coming soon...

This documentation is a work-in-progress. Please visit our [discord server](https://discord.gg/mGTq3wRQdx) with any unanswered questions in the meantime.

## Bonsai C4 Pinout

![Bonsai C4 Pinout](BonsaiC4pinout.png)

## Split Keyboard Hardware Modifications

For split keybords designed for ProMicro, there are sometimes a few wires and resistors that need to be added to make everything work. The reasons for this include:

Bonsai C4 microcontroller runs on 3.3V. This means the VCC pin is 3.3V on Bonsai C4 (and Bonsai C and Proton C) whereas VCC is 5V on a ProMicro. If your keyboard has RGB LEDs (like WS2812) which run on 5V, they normally get this 5V from the ProMicro VCC pin. When Bonsai C4 provides only 3.3V on VCC, the RGB LEDs won't work. Thus you need to omit the VCC header pin and instread wire the 5V pin of Bonsai C4 to where the VCC header pin would normally go.

Additionally, any WS2812-styele RGB LEDs will expect incoming signals to be 5V as well. Since the Bonsai C4 microcontroller can only output 3.3V, we included a single pin (A10) that bumps the 3.3V up to 5V specifically for this purpose. You'll need to wire the A10_5V pin to the "RGB data in" pin location (and omit the header pin there as well).

The ProMicro microcontroller has built-in pullup resistances that work for both I2C and half-duplex communications, whereas the STM32F chip in Bonsai C4 does not include these resistances. Thus, pullup resistors may need to be added which connect I2C and serial data lines to 3.3V (through a resistance of about 5k to 10k). For some keyboards, the keyboard PCB includes a place to install this pull up resistor (like Ergodash resistor R2), whereas for other keyboards (like Sofle, Corne, and Kyria) it may be easiest to wire up the pull up resistors directly on Bonsai C4.

# Sofle, Corne, Kyria

Photos below show how these resistances and wires should be added for Bonsai C4 for split keyboards like Sofle RGB, Corne, Kyria, etc.). They don't have to be as neat and tidy as the photos show--it was just done this way so that you can clearly see "what goes where." These modifications assume I2C is used (for an OLED for example) on ProMicro pins D1 and D0, serial RGB LEDs are used (like WS2812) on ProMicro pin D3, and split keyboard communications are ProMicro pin D2. Each of these are are independent and can be disregarded if unused (e.g. no I2C resistors needed if there is no I2C communications to an OLED). Additionally, many I2C devices may already include pull up resistors, such as small OLED screens already mounted to a PCB. If your I2C devices already include pull up resistors, you won't need to add I2C pull up resistors to Bonsai C4.

Note that similar wiring applied for other STM32F ProMicro replacements as well, like Proton C/Bonasi C.

# Ergodash

Ergodash includes a locations on the main PCBs to add pull up resistors for split communications. Simply install 10k resistors in the R2 locations on each Ergodash PCB (or install one 4.7k resistor on just one of the PCBs, it works out the same)

Ergodash does not accomodate support for any I2C devices, so there is no need for any I2C pullup resistors to be installed.


# Example pullup resistors for Sofle, Kyria, and Corne
![Bonsai C4 Pullups 1](Pullups1.jpg?raw=true)
![Bonsai C4 Pullups 1](Pullups2.jpg?raw=true)
![Bonsai C4 Pullups 1](Pullups3.jpg?raw=true)
![Bonsai C4 Pullups 1](Pullups4.jpg?raw=true)

# Example wires for Sofle, Kyria, Corne, and Ergodash
![Bonsai C4 Wires 1](Wires1.jpg?raw=true)
![Bonsai C4 Wires 2](Wires2.jpg?raw=true)
![Bonsai C4 Wires 3](Wires3.jpg?raw=true)
![Bonsai C4 Wires 4](Wires4.jpg?raw=true)
![Bonsai C4 Wires 5](Wires5.jpg?raw=true)
![Bonsai C4 Wires 6](Wires6.jpg?raw=true)

