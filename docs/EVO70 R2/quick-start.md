# Quick Start Guide

## Plugging in Your keyboard

First things first, after removing EVO70 R2 from the box (which we'll just refer to as EVO70 from here on out), grab your favorite USB-C cable and plug one end into your computer and the other end into EVO70 R2. This should immediately power on your keyboard, including the display screen which will initially feature the customMK logo.

## Display Screens

Take a moment to press on the encoder knob a few times (treat it like a switch) to cycle through the displays. One of the screens will be the Settings screen, with the default option selected of "Exit Settings". While on this screen, you can rotate the knob to access a variety of settings relevant to your keyboard, such as adjusting the lighting, date/time and formats, dimming of the LCD backlight (for LCD keyboards), etc. Get familiar with the available options, have some fun adjusting LED brightness and modes, things like that. Pretty easy, no? With EVO70, there is no need to memorize specific keys and layers to adjust your lighting settings; life is complicated enough already, and we believe that simple things should stay simple.

Do not bother setting the date or time just yet...that comes later.

While in the settings screen, encoder rotations are not sent to the computer, they are only used for adjusting settings. Outside of the settings screen, rotating the encoder will send keypresses to the computer based on whatever is assigned to it with VIA (which, by default, is volume control).

You may have noticed a Bongo cat on your way to the settings menu. To get back to the Bongo cat, first scroll back up to the "Exit Settings" menu option. Then you can press on the encoder a few times until Bongo cat shows up again. Get some metal tweezers or install a switch (any switch, it doesn't matter, it's not permanent, we got hotswaps!) and see if you can get Bongo cat to tap along with you.

Whenever you install shift key, you will be able to hold down shift while pressing the encoder knob to cycle through the available screens in reverse.

At this point, I will assume you've now set the underglow and backlight to match your desired mood, you've got some music playing playing in the background, and used your encoder knob to perfectly adjust the volume, and you have a comfy hypoallergenic digital cat ready to keep you company. Quite simply, you have the perfect environment to start building your EVO70 keyboard.

Unplug your keyboard before proceeding. If you don't feel that keyboard assembly isn't your cup of tea, there are plenty of folks who do commission builds--sometimes even on livestream; one such builder I highly recommend with extensive experience building customMK products is [The Board Father](https://www.youtube.com/channel/UCrzvOFl0guCluawgBueyGCg), also know as fraktur3#1553 on Discord who runs [8Bit Garage](https://discord.gg/kkfhaDN2gP). 

As you proceed with assembly, when in doubt, if you have any questions, feel free to drop by the [customMK Discord server](https://discord.gg/wyyw5WuEmQ) with any questions you may have.

## Disassembling the Case

It is necessary to disassemble the case to install stabilizers, and it is easier to test all the switch locations from the bottom of the PCB (which is exposed when the case is disassembled). To disassemble the case, remove the hex keys (a.k.a. Allen wrenches) from the small hardware bag that was in your EVO70 box. If you have a high profile case, you will want to use a larger hex key to remove the eight case screws from the bottom of EVO70 R2, around the permieter. If you have a low profile case, you will instead want to use a smaler hex key to remove the eight screws on the bottom that are *not* around the perimeter. At this point, the base should be removed and the bottom of the PCB is exposed. Then use a hex key to remove the encoder knob by slightly loosening the set screw visible from the side of the encoder knob (do not remove the set screw, it is unnecessary to remove it, and the set screw is very easy to lose). Then (for both high and low profile kits) use a small hex key to remove the eight small screws from the top side (these screws are found amongst the swtich locations and near the encoder). At this point, you should have a completely exposed PCB (with standoffs attached to it). The standoffs can remain attached to the PCB.

If you would like EVO70 R2 to keep track of the date and time (even when unpowered) now is a a good time to install a coin cell battery (e.g. a watch battery). EVO70 R2 will work with either a CR2023 or CR2025 coin cell battery. If you choose not to install the battery, EVO70 R2 will still operate perfectly, except that it will be unable to keep track of the date and time when unplugged/unpowered.

## VIA Setup

Now is a good time to ensure we have VIA set up to work with EVO70. EVO70 is preprogrammed to work with VIA. Using a Chromium-based browser (like Chrome or Edge) vist https://usevia.app. Then plug in the EVO70 R2 PCB to your USB cable, and click "authorized device" within VIA. VIA should recognize the EVO70 R2; approve the connection, and VIA should change to show the EVO70 layout. By default it shows the ANSI layout, but if you have an ISO layout, you can change the default settings by clicking "layouts" in the bottom left corner.

If VIA still doesn't recognize EVO70, then there is a problem of some kind. Perhaps the USB cable is a power cable and not a data cable (so try another USB cable). Perhaps there is a driver issue (so try another computer). Perhaps the firmware got erased somehow (we'll cover this later in [flashing new firmware](#flashing-new-firmware).

## Testing Switch Locations

Now is a good time to do some basic (optional) key testing. This is most easily done with a pair of metal tweezers, but really any conductive metal will do, even a paperclip or a spare mechanical switch works (but I would suggested taping down the stem of the switch so that it stays pressed). I also recommend doing this from the bottom side of the PCB simply because there is more surface area to make contact with the hotswap metal.

At the top of VIA, select KEY TESTER, and then click the box for "Test Matrix" in the bottom half of the screen. The layout on screen should match the EVO70 layout. Start testing each location by connecting across the metal contacts of each hotswap with the tweezers/switch/paperclip/etc. As you do this, each key should change color to show that it has been pressed. Once all switches locations have been tested (aside from those two switches shown in the top left of the layout), you've confirmed all switch locations are good, yay!!

If it turns out that you have an issue where 
- a single switch isn't registering keypresses
- an entire row isn't registering keypresses
- an entire column isn't registering keypresses

then unfortunately, your board has a hardware problem, probably with a bad solder joint. Not to worry though, we can usually help fix it or replace it; contact us on Discord or over email, and we'll either handle it by sending you a shipping return label, or walk you through fixing it yourself (if you are comfortable attempting a repair by soldering...please let us know as it saves you time and saves us shipping costs)

At this point, you should have a known good EVO70 R2 PCB, so congratulations! At this point, you should unplug the PCB and install the stabilizers. Then reassemble the PCB to the switch plate, ensuring all eight attachment points are fully screwed in from the top. It is recommended to insert switches while supporting the from underneath (like with a book or something)...this helps keep the PCB from flexing away from the switch plate, which could otherwise lead to bent switch pins. Once all the switches are inserted, it is a good idea to plug in the PCB again and test to confirm all the switches are inserted propertly by conducting another switch test using VIA, but this time just by pressing on the switch stems. Once you've confirmed all switches respond as expected, finish reassembling the case and add the keycaps.

If the final switch test reveals one or more problematic switches, here are some possible causes:
- If a single switch is not responding but others around it are, the switch may have a bent pin or the switch may be defecting. Remove the switch, inspect for a bent pint. Straighten any bent pins, or replace the switch.
- If straightening a bent pin or replacing a switch does not allow it to start working, it is possible that the hotswap came loose from the PCB. Inspect the back of the PCB in the switch location; if the hotswap is loose, you should be able to wiggle the metal piece of the hotswap slightly. The fix for this is to solder the hotswap in place; contact us if you need help with this.
- If several switches in an area are all not responding, it often means that the PCB in that area is too far away from the switch plate. This can happen if the screws holding the PCB and switch plate together are not fully screwed in, or if a switch (usually with bent pins) is pushing the PCB away from the switch plate in the area. Remove the problematic switches, reinserting them one at a time, and use the VIA switch tester after inserting each switch to ensure switches are being inserted successfully.

## Flashing new Firmware

Sometimes for various reasons you may wish to flash new firmware onto EVO70 R2. These reasons may include:

- You customized the firmware in QMK and want to load new firmware, perhaps to customize the splash screen logo
- You want to use VIAL instead of VIA
- Somehow your firmware went missing or is corrupted
- You have an inexplicable affinity for flashing firmware

In any case, first step is to get EVO70 in bootloader mode. A great way to do this is to remove your spacebar; underneath the spacebar is a small button; pressing that button sends the keyboard directly into bootloader mode. If you have QMK toolbox, it should recoginze the USB bootloader and be ready for you to flash new firmware. If you want to put EVO70 R2 into bootloader mode and also erase all saved settings (like keys remapped in VIA, lighting settings, sound settings, etc.), then press and hold the Escape key (top left key of the main keyboard area) while plugging in USB.

## Turning off the sound

By default, EVO70 plays an audible sound whenever it gets plugged in. You can easily disable this sound by using VIA and selecting the "audio" menu at the bottom left corner of the screen.
