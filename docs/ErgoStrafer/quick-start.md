#ErgoStrafer
ErgoStrafer is a mechanical keyboard replacement for the Merc Stealth gaming pad. It is VIA-compatible, which allows you to easily remap key assignments from a browser (no downloads required).

#VIA
No drivers need to be installed, and no dedicated software needs to be installed to remap ErgoStrafer keys with VIA. To use VIA with ErgoStrafer, simply visit https://usevia.app using a Chrome (or Chromium-based) browser. Please note that VIA does not work with Safari or Firefox at this time, as these browsers do not support the WebHID interface. With your ErgoStrafer connected to your computer, click "Authorize Device" and select "ErgoStrafer" from the list of devices shown. This establishes the connection between VIA and your ErgoStrafer.

If you wish to remap keys without a live internet connection, Vial can be downloaded and used instead of VIA, but due to underlying differences between the two, full compatibility with all features is not guaranteed.

##Key Remapping
To change a key assignment, navigate to the "Configure" tab in VIA, select the key you wish to reassign, ensure "Keymap" is selected in the top left corner of the screen, and then choose the new key assignment from the list of keys at the bottom of the screen.

There are multiple groups of keys to choose from. If you do not see your desired key at the bottom of the screen, try looking at other key groups by selecting them in the bottom left corner of the screen.

For encoders, you can assign three different keys: one that happens when the encoder is pressed, one that happens when the encoder is rotated clockwise, and one that happens when the encoder is rotated counterclockwise. Please note that VIA currently requires you to type in the keycode for each encoder assignment; a list of valid keycodes can be found here: https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md

For more detailed information on using VIA, you may find this guide helpful: https://www.keychron.com/blogs/archived/how-to-use-via-to-program-your-keyboard

##Macros
Sometimes you may want to have multiple keypresses occur in rapid succession whenever you press a key (for example: typing out your name with a single keypress). This can be achieved by using macros. To do this, assign a macro (like "M0" from the "Macro" key list) to the key you want, then select "Macros" in the top left of the screen, and configure the chosen macro with the desired keypresses.

##Layers
Layers are a very powerful feature of VIA-enabled keyboards because they allow you to override default key assignments with different key assignments. This override can be momentary (like how pressing "shift" only affects capitalization while it is actively being held) or it can be toggled (like how "caps lock" affects capitalization until it is toggled back off).

ErgoStrafer supports 32 different layers. Conceptually, this means you can create custom key mappings for up to 32 different games (or even custom key mappings for different characters within games), and ErgoStrafer will internally store and remember those key mappings, even if you plug it into a completely different computer.

How you switch between layers is entirely up to you, depending on which keys you use or don't use often. If you have already assigned all of your keys to other assignments and still wish to take advantage of layers, there are some clever options that could be done by reprogramming the QMK firmware:

-Similar to ctrl-alt-delete, you could have two or more keys pressed simultaneously that trigger a layer change.
-You could have multiple keys held down while typing in the layer number using the number keys (e.g., shift+ctrl and then press 1 then 8 to switch to layer 18).
-If you have an encoder installed, you can program it to change layers by pressing/holding down an encoder while rotating the encoder knob. The only problem with this method is that it is hard to keep track of which layer you are on; this could be overcome by playing a specific audio tune that you can relate to the layer assignment.

These are just a few of the creative approaches that can be used for layer assignments. Of course, using multiple layers is entirely optional; VIA makes reassigning keys so easy that you may find it most convenient to just remap keys manually before playing a different game. This is perfectly acceptable—the FRAM chip used to store keymap settings can handle a life of trillions of write operations, so it is practically never going to wear out from such use.

##Audio
By default, ErgoStrafer will play a brief tune when plugged in. This feature can be disabled and enabled in VIA.

To change whether audio is played upon being plugged in, go to the "Configure" tab of VIA, select "audio" in the bottom left corner, and then toggle the option to play audio upon startup.

If you want to play more advanced tunes or have them played situationally, you will need to compile and install new QMK firmware from scratch. This does require knowledge of C programming to achieve, but there are examples in the QMK GitHub repository that you can use as a guide.

##Layout Configuration
By default, VIA will show you the layout appropriate for your ErgoStrafer. However, if you flash new firmware or clear the FRAM/EEProm, you may need to toggle layout options to reconfigure your layout to match the physical hardware (e.g., whether the Z and X keys are visible, and whether rotary encoders are shown).

To change the displayed layout, go to the "Configure" tab of VIA, select "layout" in the bottom left corner, and then choose the display options that correspond to your physical hardware.

##Clearing EEProm/FRAM
If you want to reset your ErgoStrafer to factory conditions (erasing all remapped key settings), simply hold in the load key (or encoder) in the top right corner of the board while plugging in USB. This erases all the settings and puts the keyboard into bootloader mode. Then unplug USB and plug it back in to resume normal operation.

#For Developers

##Flashing New Firmware
If you have compiled new firmware from scratch using QMK, you will want to flash it to the keyboard to start using it. QMK Toolbox is recommended software for flashing updated firmware. To flash new firmware, put the ErgoStrafer into bootloader mode, select the new firmware file with QMK Toolbox, and then press "Flash" in QMK Toolbox (the flashing process may take a few seconds to complete).

There are two ways to put ErgoStrafer into bootloader mode:

Press and hold the top right key (load key) while plugging in USB. Note that this WILL clear any existing settings (key mappings), which is often desired when flashing new firmware because memory mappings can change.
Unscrew the base of the ErgoStrafer, locate the small silver button on the PCB, and press it while the board is already plugged in. This method does not erase the settings stored in EEProm/FRAM.

##Custom Development

If you are developing custom firmware for ErgoStrafer, it is recommended to use the files in the keyboards/custommk/ergostrafer folder in the QMK GitHub repository as a starting point because it contains the code used for the original factory programming (configuring switch matrix pins, FRAM, etc.).

For advanced debugging techniques while developing custom firmware, there are 5 thru holes in a straight line on the PCB which are available for SWD programming and debugging.