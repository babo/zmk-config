# Flashing UF2 Files
To flash the firmware, first put your board into bootloader mode by double clicking the reset button (either on the MCU board itself, or the one that is part of your keyboard). The controller should appear in your OS as a new USB storage device.

Once this happens, copy the correct UF2 file (e.g. left or right if working on a split), and paste it onto the root of that USB mass storage device. Once the flash is complete, the controller should unmount the USB storage, automatically restart and load your newly flashed firmware. It is recommended that you test your keyboard works over USB first to rule out hardware issues, before trying to connect to it wirelessly.

## Split keyboards
For split keyboards, only the central half (typically the left side) will send keyboard outputs over USB or advertise to other devices over bluetooth. Peripheral half will only send keystrokes to the central once they are paired and connected. For this reason it is recommended to test the left half of a split keyboard first. Please refer to split keyboards documentation for more information.

### Reset Split Keyboard Procedure

Perform the following steps to reset all parts of your split keyboard:

    1. Put each part of the split keyboard into bootloader mode.
    2. Flash one of the parts of the split with the settings reset firmware.
    3.  Repeat step 2 with the other parts of the split keyboard.
    4.  Flash the actual image for each part of the split keyboard (e.g my_board_left.uf2 to the left half, my_board_right.uf2 to the right half).

If the central and a peripheral has not paired after completing these steps, it can help to reset the central and the peripheral at around the same time. Most commonly, this is done by grounding the reset pins for each of your keyboard's microcontrollers or pressing the reset buttons, or turning both off then on with a power switch.

Once this is done, you should remove/forget the keyboard on any paired host device and pair it again, since the pairing information for them will also have been cleared from the keyboard.

The settings reset firmware has Bluetooth disabled to prevent the two sides from automatically re-pairing until you are done resetting them both. You will not be able to pair your keyboard or see it in any Bluetooth device lists until you have flashed the normal firmware again.
