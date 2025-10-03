# Flashing UF2 Files
To flash the firmware, first put your board into bootloader mode by double clicking the reset button (either on the MCU board itself, or the one that is part of your keyboard). The controller should appear in your OS as a new USB storage device.

Once this happens, copy the correct UF2 file (e.g. left or right if working on a split), and paste it onto the root of that USB mass storage device. Once the flash is complete, the controller should unmount the USB storage, automatically restart and load your newly flashed firmware. It is recommended that you test your keyboard works over USB first to rule out hardware issues, before trying to connect to it wirelessly.

## Split keyboards
For split keyboards, only the central half (typically the left side) will send keyboard outputs over USB or advertise to other devices over bluetooth. Peripheral half will only send keystrokes to the central once they are paired and connected. For this reason it is recommended to test the left half of a split keyboard first. Please refer to split keyboards documentation for more information.
