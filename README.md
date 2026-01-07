# dArkOS-G80CA

- Initial build for testing.

## Working 
- Screen
- Wifi to Mobile
- Wifi to Infrastructure (Says it's failed, but has an IP when enabling remote services).
- Joystick - Note uses DarkOS Native control scheme for games, customisations will not be made to this release to make it compatible with dArkOS Features.
- Sound

## Issues 
- LED when on Battery.
- Battery Charge Led - Bright Right
- Battery Indicator in Emulationstation is hit and miss.

## Changes
- Only to BOOT partition files with DTB updates.

## Firmware Installation
- Remove the second SD Card, or else it will fail the initial install
- Do not have the charger plugged in, as it will not reboot during the install phases

- Recommendation from ArkOS Wiki is to avoid Balana Etcher
- I have been using Raspberry Pi Imager
   - Select Operating System -> Custom (Last Option) -> Firmware File
   - Select Device

<p align="center">
<img width="681" height="486" alt="image" src="https://github.com/user-attachments/assets/ed325a9c-a293-4d29-a50c-89fc88701004" />
</p>

 - Insert SD Card and Boot
 - Blue Screen will come up, and it will reboot after expanding partitions.
 - Blue Screen will come up, and it will reboot after expanding rom.tar
 - Device will boot normally to Emulationstation
 - If you have a second ROMs card, turn off, insert the card, boot, then Options -> Advanced -> Switch to SD2 for Roms

## Keys
- No analogue tuning yet, buttons have been aligned as best as possible and joystick axis IDs and inversion status updated.

SDL Keymapping

| G80CA-MB Button     | G80CA-MB  Key SDL Code    | 
|----------------------|------------------------------|
| A Button (Right)            | Controller 00 button 00 state 1 button name a |
| B Button (Bottom)           | Controller 00 button 01 state 1 button name b |
| X Button (Top)              | Controller 00 button 02 state 1 button name x |
| Y Button (Left)             | Controller 00 button 03 state 1 button name y |
| L1 Button                   | Controller 00 button 09 state 1 button name leftshoulder |
| R1 Button                   | Controller 00 button 10 state 1 button name rightshoulder |
| L2 Button                   | Controller 00 axis 04 value 32767 axis name lefttrigger |
| R2 Button                   | Controller 00 axis 05 value 32767 axis name righttrigger |
| L3 Button                   | Joystick   00 button 14 state 1 |
| R3 Button                   | Joystick   00 button 15 state 1 |
| D-Pad Up                    | Controller 00 button 11 state 1 button name dpup |
| D-Pad Down                  | Controller 00 button 12 state 1 button name dpdown|
| D-Pad Left                  | Controller 00 button 13 state 1 button name dpleft |
| D-Pad Right                 | Controller 00 button 14 state 1 button name dpright |
| Start Button                | Joystick   00 button 13 state 1  |
| Select Button               | Joystick   00 button 12 state 1 |
| Function Button             | Joystick   00 button 16 state 1 |
| Left Analogue Up            | Controller 00 axis 01 value -32767 axis name lefty |
| Left Analogue Down          | Controller 00 axis 01 value +32768 axis name lefty |
| Left Analogue Left          | Controller 00 axis 00 value -32767 axis name leftx |
| Left Analogue Right         | Controller 00 axis 00 value +32768 axis name leftx |
| Right Analogue Up           | Controller 00 axis 02 value +32767 axis name rightx |
| Right Analogue Down         | Controller 00 axis 02 value -32768 axis name rightx |
| Right Analogue Left         | Controller 00 axis 03 value +32767 axis name righty |
| Right Analogue Right        | Controller 00 axis 03 value -32768 axis name righty) |

## Second SD Card 
- It was hit and miss until I went and selected the option under advanced (at the bottom).
