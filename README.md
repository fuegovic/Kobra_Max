Marlin firmware for the AnyCubic Kobra Max.
Based off Marlin 2.0.8 (bugfix)

# Note
The compiled version is in [/workspace/firmware.bin](https://github.com/fuegovic/Kobra_Max/blob/master/workspace/firmware.bin)
- Removed startup jingle, otherwise same as https://github.com/wabbitguy/Kobra_Max

# Important - READ THIS

If you are getting great prints from your Kobra Max keep in mind that you can't fix something that's not broken. Updating your firmware may void your warranty and may or may not perform exactly as you expect it to. Thus, firmware updates are at your own risk.

You will be using a host via USB to complete the firmware update (Repetier Server Pro, Octoprint, Pronterface, etc) if you are using the AnyCubic stock firmware. If you are updating from a prior release of mine or Zombie's firmware release only re-flashing the firmware is needed. I.e. don't do the M502/M500 from a host.

The firmware here was designed to work with Anycubic's original Tri-Gorilla_ProA V1.0.4 motherboard and a Nextion LCD that uses a DWIN_FOLDER. Anycubic has changed their production run so new Kobra Max's (and this might include the Kobra Series) with a Tri-Gorilla_ProB V1.0.2. There have been reports of the original firmware not working on the newer production or replacement motherboards. To determine which motherboard you have, the original uses a USB type B, the newer motherboards use a micro USB connector. The photo shows the difference.

<img width="712" alt="Kobra_Max 2023-08-02 10-59-02" src="https://github.com/wabbitguy/Kobra_Max/assets/8953419/fb21433e-a221-41a9-8b69-c885f36b89a9">

# Update Procedure

1. Power off the Kobra Max
2. Remove any USB cable attached to the printer
3. Download the "firmware.bin" file from the releases
4. Copy the *firmware.bin* file to a blank microSD card (one that's known to work on the printer)
5. Put the microSD in the correct slot on the printer (not the slot on the LCD display)
6. Power up the printer

The animation graphic will appear on the LCD, within 10 seconds you will hear five beeps from the printer and the LCD will display the main menu.
*NOTE* The printer may hang during this update, power down, wait 10 seconds and repeat with power up (it can take two or three times to work)

7. Remove microSD card
8. Power down the printer, wait 10 seconds, power up again. Wait for the main menu to appear before continuing.

----- only contnue if updating from the AnyCubic factory stock firmware -----

9. Connect Pronterface via USB to the Kobra Max and make the serial/usb connection.

[Pronterface Download](https://github.com/kliment/Printrun/releases/tag/printrun-2.0.0rc8)

10. In Pronterface "Command to send" area, type in M502 and click the SEND button. Do this *TWICE*
11. Type in M500 and click SEND.
12. Disconnect Pronterface and unplug the USB cable (not needed)
13. Use the LCD Prepare-->Levelling-->Auto Level
14. Firmware Update complete.

eSteps for extrusion, any PID tuning may have to be redone

# Firmware Changes

1. Levelling grid is now 7 x 7 for a 49 point system (was 25 points)
2. Babystepping Z-offset is 0.01mm (was 0.05mm)
3. M600 gcode supported for filament changes. Both layer based and within a single layer
4. Maximum extrude length 800mm (to allow for loading and unloading filament full length of bowden tube)
5. Max bed temp 120C - increased temp rise time to compensate for slow heating rate as temp rises (not all will achieve high temps)
6. Default feedrates and acceleration have been increased
7. Firmware version info indicates enabled items
8. For PREPARE, filament load/unload has been automated for release 1.3

CJ = Classic Jerk
LA = Linear Advance
JD = Junction Deviation

After considerable testing with Linear Advance, this version has it disabled. The 30% extra printing time when it was enabled wasn't offset near enough by the minimal quality increase.

# Filament Change Procedure

When the printer receives the M600 filament change GCODE:
1. The hot end will lift and move to the back left corner (called the park position).
2. The filament will then retract all the way back to the extruder to allow you to remove it.
3. Insert the new filament approximately 1 to 2" just past the extruder output; do NOT push the filament all the way to the hot end!)
4. On the LCD Status display press the  "RESUME" button.
5. Filament will feed all the way to the hot end, and purge approximately 40mm to ensure accurate change
6. Wipe the nozzle, printer will then automatically return to the original, lower and resume printing

*Note* after purging/wiping there is a slight delay before the hot end returns to the print job. Be patient. Some hold a metal spatula under it so it doesn't drip.

# Filament Printing Examples

![alt-text](https://github.com/wabbitguy/Kobra_Max/blob/master/images/layer_change.jpg)

![alt-text](https://github.com/wabbitguy/Kobra_Max/blob/master/images/single_layer_change.jpg)

![alt-text](https://github.com/wabbitguy/Kobra_Max/blob/master/images/end_result.jpg)

