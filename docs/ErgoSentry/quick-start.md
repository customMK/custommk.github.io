# ErgoSentry

ErgoSentry is a mechanical keyboard replacement for the Merc Stealth gaming pad. It is VIA-compatible, which allows you to easily remap key assignments from a browser (no downloads required). There are currently three versions of ErgoSentry, called ErgoSentry ANSI, ErgoSentry Plus ANSI, and ErgoSentry Plus ISO.

# VIA

No drivers need to be installed, and no dedicated software needs to be installed to remap ErgoSentry keys with VIA. To use VIA with ErgoSentry, simply visit https://usevia.app using a Chrome (or Chromium-based) browser. Please note that VIA does not work with Safari or Firefox at this time, because these browsers do not support the WebHID interface. With your ErgoSentry connected to your computer, click "Authorize Device" and select your keyboard from the list of devices shown. This establishes the connection between VIA and your ErgoSentry.

## Temporary note regarding ErgoSentry and VIA

VIA has not yet been fully updated to include ErgoSentry (but it is in progress). Thus, to use VIA with ErgoSentry, you will need to load a simple text file that tells VIA a few details about ErgoSentry. This process is called "loading a JSON file" and the JSON file informs VIA which keys exist for this keyboard and what features are available (like RGB lighting).

Here are the JSON files you'll need for each ErgoSentry; right click, download, and save in a convenient location the one matching your keyboard:
[ErgoSentry ANSI JSON file](https://raw.githubusercontent.com/customMK/custommk.github.io/master/docs/ErgoSentry/ergosentry_ansi.json)
[ErgoSentry Plus ANSI JSON file](https://raw.githubusercontent.com/customMK/custommk.github.io/master/docs/ErgoSentry/ergosentry_plus_ansi.json)
[ErgoSentry Plus ISO JSON file](https://raw.githubusercontent.com/customMK/custommk.github.io/master/docs/ErgoSentry/ergosentry_plus_iso.json)

[This page](https://docs.cannonkeys.com/via-json-loading/) shows you how to upload the JSON file to VIA. Once that is complete, VIA should allow you to "Authorize Device" for your ErgoSentry.

## Using VIA without an internet connection
If you wish to remap keys without a live internet connection, you can find a downloadable version of VIA at https://github.com/the-via/releases/releases, or Vial can be used instead of VIA--but due to underlying differences between Vial and VIA, full compatibility with all features is not guaranteed.

## Key Remapping

To change a key assignment, navigate to the "Configure" tab in VIA, select the key you wish to reassign, ensure "Keymap" is selected in the top left corner of the screen, and then choose the new key assignment from the list of keys at the bottom of the screen.

There are multiple groups of keys to choose from. If you do not see your desired key at the bottom of the screen, try looking at other key groups by selecting them in the bottom left corner of the screen.

For encoders, you can assign three different keys: one that happens when the encoder is pressed, one that happens when the encoder is rotated clockwise, and one that happens when the encoder is rotated counterclockwise. Please note that VIA currently requires you to type in the keycode for each encoder assignment; a list of valid keycodes can be found here: https://github.com/qmk/qmk_firmware/blob/master/docs/keycodes.md

For more detailed information on using VIA, you may find this guide helpful: https://www.keychron.com/blogs/archived/how-to-use-via-to-program-your-keyboard

## Macros

Sometimes you may want to have multiple keypresses occur in rapid succession whenever you press a key (for example: typing out your name with a single keypress). This can be achieved by using macros. To do this, assign a macro (like "M0" from the "Macro" key list) to the key you want, then select "Macros" in the top left of the screen, and configure the chosen macro with the desired keypresses.

## Layers

Layers are a very powerful feature of VIA-enabled keyboards because they allow you to override default key assignments with different key assignments. This override can be momentary (like how pressing "shift" only affects capitalization while it is actively being held) or it can be toggled (like how "caps lock" affects capitalization until it is toggled back off).

ErgoSentry supports 12 different layers. Conceptually, this means you can create custom key mappings for up to 12 different games (or even custom key mappings for different characters within games), and ErgoSentry will internally store and remember those key mappings, even if you plug it into a completely different computer.

How you switch between layers is entirely up to you, depending on which keys you use or don't use often. Using multiple layers is entirely optional; VIA makes reassigning keys so easy that you may find it most convenient to just remap keys manually before playing a different game. This is perfectly acceptable—the FRAM chip used to store keymap settings can handle a life of trillions of write operations, so it is practically never going to wear out from such use.

## RGB limitations

Officially, the USB 2.0 specifcation permits devices (like keyboards) to draw up to 0.5 amps of current. As-shipped, ErgoSentry has the RGB brigthness set to 50% of the maximum capacity, which should work for all USB ports. However, it is entirely possible to exceed the 0.5 amp threshold by increasing up the RGB brightness. Some USB ports (like the blue USB 3.0 ports) may be able to deliver enough current to run the LEDs at the maximum brightness.

If you exceed the current limit for USB ports on your computer, the keyboard will appear to "lock up" and be unresponsive to keypresses and changing settings. To overcome this issue, you can try another USB port which may be able to provide more power (e.g. one with a blue interior, one on a powered USB hub, one on the back of the computer, etc.).

If you don't have a USB port that provide enough current, you can instead reset the keyboard to factory-default settings (note: this will erase any settings you may have changed in VIA). To do this, simply hold the Esc key while plugging in USB, then unplug and plug it back in with no keys pressed.

## USB Audio

ErgoSentry includes high performance USB audo ports based on the Cmedia CM6646 chip, supporting headphone audio up to 192kHz/32bits. There are dedicated stero microphone and headphone ports using TRS connectors, and we also include a splice for compatibility with headsets that use TRRS combo plugs (which combine both mic and headphone in a single connector, but be aware that this method only allows for mono microphone capability).

By default, the top right most key of the keyboard is set to mute the microphone input. This mute capability happens at the hardware level within ErgoSentry itself, and thus does not involve the operating system at all. This means that it will work regardless of your operating system or application that you are running. The current mute state is indicated by the red mute LED just above the microphone mute key.

If you already have a dedicated sound card you prefer to use, and thus do *not* want to use the USB audio capability built into ErgoSentry, you can fully disable the USB audio capability in ErgoSentry. By default, enabling and disabling USB audio is toggled by pressing the top right rotary encoder. Whenever USB audio is enabled, the mic mute LED will flash a few times while the audio chip boots up. While the USB audio is disabled, pressing mic mute will have no effect

## Audio chime

By default, ErgoSentry will play a brief tune when plugged in. This feature can be disabled and enabled in VIA.

To change whether audio is played upon being plugged in, go to the "Configure" tab of VIA, select "audio" in the bottom left corner, and then toggle the option to play audio upon startup.

If you want to play more advanced tunes or have them played situationally, you will need to compile and install new QMK firmware from scratch. This requires knowledge of C programming to achieve, but there are examples in the QMK GitHub repository that you can use as a guide.

## Layout Configuration

By default, VIA will show you the layout appropriate for your ErgoSentry. However, if you flash new firmware or clear the FRAM/EEProm, you may need to toggle layout options to reconfigure your layout to match the physical hardware (e.g., whether the Z and X keys are visible, and whether rotary encoders are shown).

To change the displayed layout, go to the "Configure" tab of VIA, select "layout" in the bottom left corner, and then choose the display options that correspond to your physical hardware.

## Clearing EEProm/FRAM Settings

If you want to reset your ErgoSentry to factory conditions (erasing all remapped key settings), simply hold in the Esc key (specifically the location where the Esc would normally be, in case it was remapped elsewhere) of the board while plugging in USB. This erases all the settings and puts the keyboard into bootloader mode. Then unplug USB and plug it back in to resume normal operation.

# For Developers

## Flashing New Firmware

If you have compiled new firmware from scratch using QMK, you will want to flash it to the keyboard to start using it. QMK Toolbox is recommended software for flashing updated firmware. To flash new firmware, put the ErgoSentry into bootloader mode, select the new firmware file with QMK Toolbox, and then press "Flash" in QMK Toolbox (the flashing process may take a few seconds to complete).

There are two ways to put ErgoSentry into bootloader mode:

Press and hold the Esc key while plugging in USB. Note that this WILL clear any existing settings (e.g. key mappings), which is often desired when flashing new firmware because memory mappings can change.
Remove the spacebar of the ErgoSentry, locate the small button hidden below the spacebar, and press it while the board is already plugged in. This method does not erase the settings stored in EEProm/FRAM.

## Custom Development

If you are developing custom firmware for ErgoSentry, it is recommended to use the files in the keyboards/custommk/ folder in the QMK GitHub repository as a starting point because it contains the code used for the original factory programming (configuring switch matrix pins, FRAM, etc.). If you want to compile firmwarw with VIA compability, you will also need to use the customMK QMK Userspace, since QMK has removed all VIA keymaps from the QMK official repository.

For advanced debugging techniques while developing custom firmware, there are 5 thru holes in a straight line on the PCB which are available for SWD programming and debugging.