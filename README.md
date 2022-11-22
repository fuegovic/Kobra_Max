Marlin firmware for the AnyCubic Kobra Max.
Based off Marlin 2.0.8 (bugfix)

# Important - READ THIS

If you are getting great prints from your Kobra Max keep in mind that you can't fix something that's not broken. Updating your firmware may void your warranty and may or may not perform exactly as you expect it to. Thus, firmware updates are at your own risk.

`The PAUSE button in the LCD Print Ststus display has been repurposed to allow for filament changes. If you require this pause button to actually pause the printer, do not update the firmware!`

You will be using a host via USB to complete the firmware update (Repetier Server Pro, Octoprint, Pronterface, etc).

## Update Procedure

1. Power off the Kobra Max
2. Remove any USB cable attached to the printer
3. Download the "firmware.bin" file from the releases
4. Copy the *firmware.bin* file to a blank microSD card (one that's known to work on the printer)
5. Put the microSD in the correct slot on the printer (not the slot on the LCD display)
6. Power up the printer
7. 
... The animation graphic will appear on the LCD, within 10 seconds you will hear five beeps from the printer and the LCD will display the main menu.
... *NOTE* The printer may hang during this update, power down, wait 10 seconds and repeat with power up (it can take two or three times to work)

7. Remove microSD card
8. Power down the printer, wait 10 seconds, power up again. Wait for the main menu to appear before continuing.
9. Connect Pronterface via USB to the Kobra Max and make the serial/usb connection.
10. 
... [Pronterface Download] (https://github.com/kliment/Printrun/releases/tag/printrun-2.0.0rc8)

10. In Pronterface "Command to send" area, type in M502 and click the SEND button. Do this *TWICE*
11. Type in M500 and click SEND.
12. Disconnect Pronterface and unplug the USB cable (not needed)
13. Use the LCD Prepare-->Levelling-->Auto Level
14. Firmware Update complete.

... eSteps for extrusion, any PID tuning may have to be redone

## Firmware Changes

1. Levelling grid is now 7 x 7 for a 49 point system (was 25 points)
2. Babystepping Z-offset is 0.01mm (was 0.05mm)
3. 
