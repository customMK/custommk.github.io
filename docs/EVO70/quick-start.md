# Quick Start Guide

## Plugging in Your keyboard

First things first, after removing EVO70 from the box, grab your favorite USB-C cable and plug one end into your computer and the other end into EVO70. This should immediately power on your keyboard, including the OLED screen which will feature the customMK logo as a splash screen.

## OLED Menu

Take a moment to press on the encoder knob a few times (treat it like a switch) to cycle through the menu options. Get familiar with the available options, have some fun adjusting LED brightness and modes, things like that. Pretty easy, no? With EVO70, there is no need to memorize specific keys and layers to adjust your lighting settings; life is complicated enough already, and we believe that simple things should stay simple.

Note the menu mysterious menu item labeled "custom"...this refers to a custom assignment of your choosing. That is, using VIA you can assign whatever key or macro you like to encoder clockwise and coutnerclockwise rotations, just like how you can assign any other key on your keyboard. But we'll get to VIA in a minute

The last menu item is the illustrious Bongo cat. Get some metal tweezers or install a switch (any switch, it doesn't matter, it's not permanent, we got hotswaps!) and see if you can get Bongo cat to tap along with you.

Whenever you install shift key, you will be able to hold down shift while clicking the encoder knob to traverse the menu in reverse.

At this point, I will assume you've now set the underglow and backlight to match your desired mood, you've got some music playing playing in the background, and used your encoder knob to perfectly adjust the volume, and you have a comfy hypoallergenic OLED cat ready to keep you company. Quite simply, you have the perfect environment to start building your EVO70 keyboard.

Unplug your keyboard before proceeding. If you prefer to see a video overview of the assembly process, I highly recommend [this one](https://www.youtube.com/watch?v=ZvaERQcjjN4) by [Cojoc Duc](https://www.youtube.com/channel/UCHn1rPc0_peNq8eHFtSbOHA). And if you ultimately decide keyboard assembly isn't your cup of tea, there are plenty of folks who do commission builds--sometimes even on livestream; one such builder I highly recommend with extensive experience building customMK products is [The Board Father](https://www.youtube.com/channel/UCrzvOFl0guCluawgBueyGCg), also know as fraktur3#1553 on Discord who runs [8Bit Garage](https://discord.gg/kkfhaDN2gP)

As you proceed with assembly, when in doubt, if you have any questions, feel free to drop by the [customMK Discord server](https://discord.gg/wyyw5WuEmQ) with any questions you may have.

## Disassembling the Case

It is necessary to disassemble the case to install stabilizers, and it is easier to test all the switch locations from the bottom of the PCB (which is exposed when the case is disassembled). To disassembled the case, remove the hex keys (a.k.a. Allen wrenches) from the small hardware bag that was in your EVO70 box. One of the hex keys should fit nicely in the case screws located around the perimeter of EVO70. Unscrew the eight perimeters screws, either from top side or the bottom side. My apologies if you find some of the screws to be a bit tight; I asked the assemblers to do the final tighening gently by hand (instead of electric screwdriver) but they apparently didn't get the memo this time.

Once you've gotten eight case screws removed, you should be able to see the lovely EVO70 PCB. To install the stabilizers, you will need to separate the PCB from the switch plate. There are smaller hex keys needed to do this, which you will find in the hardware bag. Just unscrew six screws holding the plate and PCB together (only needing to unscrew from one side).

To separate the PCB from the switch plate, you will also find it necessary to remove the knob from the encoder. To do this, use the same hex key (allen wrench) as you used on the case screws. On the side of the encoder knob you will find a small hole with a set screw inside of it; this is where the hex key goes. **Just a fraction of a turn to loosen the set screw is all that should be needed.** I don't recommend removing the set screw from the knob completely, both because it is unnecessary to do so, and because the set screw is very tiny and can get lost easily.


## VIA Setup

Now is a good time to ensure we have VIA set up to work with EVO70. EVO70 is preprogrammed to work with VIA, but VIA...well, it's proprietary, closed-source software, which they update at their own pace. It will likely take several months from now (April 2022) before VIA automatically recognizes EVO70. In the meantime, we have to "tell" VIA what an EVO70 is, every time we open up VIA. (Yes, it is annoying and frustrating, and we may switch to Vial in the future to solve that problem). To teach VIA what an EVO70 is, we simply import a small text file (called a JSON file) which describes the EVO70 layout. It's just a simple, harmless text file, you can open it up in a file editor to have a look if your'e curious. [Here](https://raw.githubusercontent.com/customMK/custommk.github.io/master/docs/EVO70/evo70_via.json) is the JSON file you need; right click, download and save it somewhere convenient.

Once you have VIA up and running (assuming you've already downloaded it from [caniusevia.com](https://caniusevia.com) and run it), in the menu in the very top left corner ("File" menu on Windows, "VIA" menu on MacOS) select "Import Keymap". Find the JSON file you downloaded and press OK. That's all, VIA will now know what an EVO70 is (at least until you close VIA).

Plug in the EVO70 PCB to your USB cable. VIA may immediately recognized that you have an EVO70 plugged in. If not, unplug EVO70 and plug it back in (sometimes VIA doesn't catch it on the first attempt, and I'm not sure why).

If VIA still doesn't recognize EVO70, then there is a problem of some kind. Perhaps the USB cable is a power cable and not a data cable (so try another USB cable). Perhaps there is a driver issue (so try another computer). Perhaps the firmware got erased somehow (we'll cover this later in [flashing new firmware](#flashing-new-firmware).

## Testing Switch Locations

If VIA does recognize EVO70, we're ready to do some key testing. This is a **highly recommended** activity before beginning to install stabs, switches, and keycaps is to test each switch location. This is most easily done with a pair of metal tweezers, but really any conductive metal will do, even a paperclip or a spare mechanical switch works (but I would suggested taping down the stem of the switch so that it stays pressed). I recommend doing this from the bottom side of the PCB simply because there is more surface area to make contact with the hotswap metal.

At the top of VIA, select KEY TESTER, and then click the box for "Test Matrix" at the bottom. The layout on screen should match the EVO70 layout. Start testing each location by connecting across the metal contacts of each hotswap with the tweezers/switch/paperclip/etc. As you do this, each key should change color to show that it has been pressed. Once all switches locations have been tested (aside from those two switches shown in the top left of the layout), you've confirmed all switch locations are good, yay!!

If it turns out that you have an issue where 
- a single switch isn't registering keypresses
- an entire row isn't registering keypresses
- an entire column isn't registering keypresses

then unfortunately, your board has a hardware problem, probably with a bad solder joint. Not to worry though, we can usually help fix it or replace it; contact us on Discord or over email, and we'll either handle it by sending you a shipping return label, or walk you through fixing it yourself (if you are comfortable attempting a repair by soldering...please let us know as it saves you time and saves us shipping costs!)

At this point, you should have a known good EVO70 PCB, congratulations! At this point, you should unplug the PCB and add the stabilizers. Then reassemble the PCB to the switch plate, ensuring all six attachment points are fully screwed in from both the top and the bottom. It is recommended to insert switches into the switch plate and PCB with the PCB lying flat against a surface. This helps prevent the PCB from flexing away from the switch plate (which can bend pins and keep switches from making good electrical contact). Once all the switches are inserted, it is a good idea to plug in the PCB again and test to confirm all the switches are inserted propertly by conducting another switch test using VIA, but this time just by pressing on the switch stems. Once you've confirmed all switches respond as expected, finish reassembling the case and add the keycaps.

If the final switch test reveals one or more problematic switches, here are some possible causes:
- If a single switch is not responding but others around it are, the switch may have a bent pin or the switch may be defecting. Remove the switch, inspect for a bent pint. Straighten any bent pins, or replace the switch.
- If straightening a bent pin or replacing a switch does not cause it to start working, it is possible that the hotswap came loose from the PCB. Inspect the back of the PCB in the switch location; if the hotswap is loose, you should be able to wiggle the metal piece of the hotswap slightly. The fix for this is to solder the hotswap in place; contact us if you need help with this.
- If several switches in an area are all not responding, it often means that the PCB in that area is too far away from the switch plate. This can happen if the screws holding the PCB and switch plate together are not fully screwed in, or if a switch (usually with bent pins) is pushing the PCB away from the switch plate in the area. Remove the problematic switches, reinserting them one at a time, and use the VIA switch tester after inserting each switch to ensure switches are being inserted successfully.

## Installing the Rubber Feet

There are three large rubber feet included in the box with your EVO70. With a little bit of squishing, they will pop snugly into the three holes in the EVO70 base. The feet are pretty durable; there is no need to be timid when inserting them. 

## Flashing new Firmware

Sometimes for various reasons you may wish to flash new firmware onto EVO70. These reasons may include:

- You customized the firmware in QMK and want to load new firmware, perhaps to customize the splash screen logo
- You want to use VIAL instead of VIA
- Somehow your firmware went missing or is corrupted
- You have an inexplicable affinity for flashing firmware

In any case, first step is to get EVO70 in bootloader mode. A great way to do this is to remove your spacebar; underneath the spacebar is a small button; pressing that button sends the keyboard directly into bootloader mode. If you have QMK toolbox, it should recoginze the USB bootloader and be ready for you to flash new firmware. Because of the use of EEPROM, in QMK Toolbox it is generally a good idea to first press "Clear EEPROM" (and disregard the "FAIL" message) before pressing "Flash" (whch should report "Success").

If your order number is CMK-1462 or lower and your order shipped in April 2022, it is highly recommended that you flash new firmware onto your EVO70, as there were some findings post-shipment arising from the late addition of Bongo Cat. The newer firmware offers better OLED on/off control, more control over backlight breathing, correction to encoder assignment in VIA, and the ability to remember the OLED state and backlight breathing even after unplugging EVO70.

Here are two versions of VIA-compatible firmware you can upgrade to. The first one includes Bongo Cat, whereas the second one includes scroll wheel capability. The scroll wheel feature uses the "mouse keys" capabilities which does not fit in the firmware if Bongo Cat is present.

[EVO70 firmware with Bongo Cat](https://raw.githubusercontent.com/customMK/custommk.github.io/master/docs/EVO70/custommk_evo70_via_bongo.hex)

[EVO70 firmware with scroll wheel](https://raw.githubusercontent.com/customMK/custommk.github.io/master/docs/EVO70/custommk_evo70_via_scroll.hex)


If you'd prefer to use Vial instead of VIA, Garbs#7637 on our Discord server created Vial firmware for EVO70. One amazing feature of Vial is that you never need to load a JSON file (since the keyboard stores that information internally). The firmware Garbs provides disables the per-key backlighting, but retains underglow (with limited modes), includes Bongo Cat, and enables the QMK settings menu in Vial:
[EVO70 Vial firmware by Garbs](https://drive.google.com/file/d/193uHYtFOC7zEp4uPulkanuvZ_nH_SVBr/view?usp=sharing)

## Customizing the splash screen

This is a "to do" item. I have ideas for how to make this easy (without a full recompile of QMK firmware) but it's not implemented. Unless/until that happens the only viable option to do it yourself is to download and install QMK, swap out customMK logo graphic for your own, and recompile. Not great, not terrible....but not as easy as we'd prefer it to be, in any case. You will find the splash green graphic assigned to the "splash" variable [here](https://github.com/customMK/qmk_firmware/blob/evo70/keyboards/custommk/evo70/evo70.c)

In the interim, if you've got a monochrome 128x32 image all ready to go, I may choose to accomodate reasonable requests for firmware with a custom splash screen, just in case you find compiling QMK to be intimidating. No guarantees if you go this route (because it may easily become too overwhelming for me to keep up), please be patient, and please make this as easy for me as possible by using [image2cpp](https://javl.github.io/image2cpp/) to prepare the image using the steps below:

- create a monochrome 128x32 image (technically this step is optional, image2cpp can convert to monochrome and rescale if needed, but if you want the most control over how this is done, use image editing software)
- upload the resulting image to image2cpp
- set the canvas size to 128x32 (required)
- make sure the preview looks **exactly** like what you want for the splash screen
- press "Generate code" at the bottom
- copy the generated code at the bottom of the screen (should start with something like "const unsigned char" and have a bunch of numbers like 0x00)
- send me the generated code via email