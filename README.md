# dArkOS-G80CA

**dArkOS build optimized for G80CA / G80CA-MB devices**  
(RK3326-based R36S/RG351MP-style clones)

This version of [dArkOS](https://github.com/christianhaitian/dArkOS) is designed to provide the purest dArkOS experience on G80CA hardware.

The main differences from stock RG351MP builds are hardware-specific adjustments to make future updates and maintenance easier.  
The **only** component out of sync with upstream dArkOS is the **Battery LED Service** script due to the G80CA LED GPIOS and dual red/blue LED hardware.

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/southoz/dArkOS-G80CA?style=flat-square)](https://github.com/southoz/dArkOS-G80CA/releases)
[![GitHub stars](https://img.shields.io/github/stars/southoz/dArkOS-G80CA?style=flat-square)](https://github.com/southoz/dArkOS-G80CA/stargazers)

## ✅ What's Working

- Screen
- Wi-Fi
- Joysticks (uses **dArkOS native** control scheme for games & EmulationStation)
- Sound (speakers + headphones)
- Battery LED behaviour:  
  **Blue** ≥ 20% • **Blinking Red** < 20%

## ⚠️ Known Issues

- Battery percentage indicator initially incorrect in Emulationstation
- Reboot doesn't work when the device is plugged in to charger, stays at Battery DTB Screen

## ⚠️ Important Installation Warnings

Before flashing — **very important** to avoid bricking or failed installs:

- **Remove the second SD card** (ROMs card) before starting installation
- **Do NOT** have the charger plugged in during the whole flashing & first-boot process
- The ArkOS Wiki recommends **avoiding Balena Etcher** for this device (many users report failures)

## Step-by-Step Installation

1. Download the latest image from:  
   → [Releases page](https://github.com/southoz/dArkOS-G80CA/releases)

2. Extract the `.img` file using **7-Zip** (or similar)

3. Verify the file integrity (recommended):  
   Compare the hash with the value published in the release notes

4. Flash the image to a good quality microSD card using one of these tools (all confirmed working):
   - USB Image Tool
   - Raspberry Pi Imager
   - Rufus (Windows)
   - **Avoid** Balena Etcher if possible

5. Insert the card (no second ROM card yet) → power on

6. First boot:  
   → Blue screen appears → device expands partitions → auto-reboots

7. Second boot:  
   → Blue screen again → expands `roms.tar` to EASYROMS partition → auto-reboots

8. Final boot → you should land in EmulationStation

### Adding ROMs on second SD card (optional)

- Power off completely
- Insert your ROMs SD card
- Boot the device
- Press **START** → **Options** → **Advanced** → **Switch to SD2 for Roms**

## 🎮 Controller / Key Mapping (SDL)

Buttons have been aligned as closely as possible to the **RG351MP** layout.  
Analogue tuning is not yet implemented.

| G80CA Button          | SDL Mapping / Name                  | Type / Value          |
|-----------------------|-------------------------------------|-----------------------|
| A (Right)             | `a`                                 | button 00             |
| B (Bottom)            | `b`                                 | button 01             |
| X (Top)               | `x`                                 | button 02             |
| Y (Left)              | `y`                                 | button 03             |
| L1                    | `leftshoulder`                      | button 09             |
| R1                    | `rightshoulder`                     | button 10             |
| L2                    | `lefttrigger`                       | axis 04 → 32767       |
| R2                    | `righttrigger`                      | axis 05 → 32767       |
| L3                    | —                                   | button 14             |
| R3                    | —                                   | button 15             |
| D-Pad Up              | `dpup`                              | button 11             |
| D-Pad Down            | `dpdown`                            | button 12             |
| D-Pad Left            | `dpleft`                            | button 13             |
| D-Pad Right           | `dpright`                           | button 14             |
| Start                 | —                                   | button 13 (Joystick)  |
| Select                | —                                   | button 12 (Joystick)  |
| Function              | —                                   | button 16 (Joystick)  |
| Left Analog (all dir) | `leftx` / `lefty`                   | axis 00 / 01          |
| Right Analog (all dir)| `rightx` / `righty`                 | axis 03 / 02          |

**Note:** Axis directions/inversions have been adjusted to match typical RG351MP expectations.

## Related Projects & Thanks

- [dArkOS main project](https://github.com/christianhaitian/dArkOS) – huge thanks to christianhaitian!
- Community discussions: r/R36S, r/SBCGaming, Retro Handhelds groups

Feel free to report issues or suggest improvements in the [Issues tab](https://github.com/southoz/dArkOS-G80CA/issues).  
Happy retro gaming! 🎮
