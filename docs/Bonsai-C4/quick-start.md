# Coming soon...

We're in the process of setting up this documentation, please visit our [discord server](https://discord.gg/mGTq3wRQdx) with any questions in the meantime

## Split Keyboard Modifications

For split keybords designed for ProMicro, there are usually a few wires and resistors that need to be added to make everything work. The reasons for this include:

Bonsai C4 lives in a 3.3V world (VCC = 3.3V) but ProMicro is 5V. If your board has RGB LEDs which expect 5V power, you need to omit the VCC header pin and wire the 5V pin of Bonsai C4 to where the VCC header pin would normally go.

Those same RGB LEDs expect incoming signals to be 5V as well, but Bonsai C4 lives and breathes 3.3V. But we included a single pin (A10) that bumps the 3.3V up to 5V, and you'll need to wire that pin to the RGB data in location (and omit the header pin there as well).

ProMicro has some reasonable built-in pullup resistances for I2C and half-duplex communications, whereas the STM32F chip in Bonsai C4 does not include these resistances. Thus, pullup resistors need to be added which connect I2C and serial data lines to 3.3V (through a resistance of about 5k to 10k).

The photos below show how these resistances and wires should be added for Bonsai C4 for most split keyboards (Sofle RGB, Corne, Kyria, etc.). They don't have to be as neat and tidy as the photos show--it was just done this way so that you can clearly see "what goes where." These modifications assume I2C is used (for an OLED for example) on ProMicro pins D1 and D0, serial RGB LEDs are used (like WS2812) on ProMicro pin D3, and split keyboard communications are ProMicro pin D2. Each of these are are independent and can be disregarded if unused (e.g. no I2C resistors needed if there is no I2C communications to an OLED)

Note that similar wiring applied for other STM32F ProMicro replacements as well, like Proton C/Bonasi C.

![Bonsai C4 Pullups 1](Pullups1.jpg?raw=true)
![Bonsai C4 Pullups 1](Pullups2.jpg?raw=true)
![Bonsai C4 Pullups 1](Pullups3.jpg?raw=true)
![Bonsai C4 Pullups 1](Pullups4.jpg?raw=true)
![Bonsai C4 Wires 1](Wires1.jpg?raw=true)
![Bonsai C4 Wires 2](Wires1.jpg?raw=true)
![Bonsai C4 Wires 3](Wires1.jpg?raw=true)
![Bonsai C4 Wires 4](Wires1.jpg?raw=true)
![Bonsai C4 Wires 5](Wires1.jpg?raw=true)