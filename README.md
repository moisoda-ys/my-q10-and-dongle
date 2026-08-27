# Q10 + Macintosh dongle

This repository builds a ZMK split configuration for a ZitaoTech Q10 and the
Macintosh-style nRF52840 dongle.

The dongle is the split central: connect it to Windows 11 over USB. The Q10
connects to the dongle over Bluetooth and keeps the original Q10 keymap.

## Firmware artifacts

GitHub Actions builds four UF2 files:

- `sofle_dongle-zmk.uf2` - flash this to the Macintosh dongle.
- `zitaotech_q10-zmk.uf2` - flash this to the Q10.
- The two `settings_reset` artifacts erase saved Bluetooth/settings data.

Flash each device by holding its existing bootloader button until the UF2
drive appears, then copying the matching file to that drive.

## First pairing

Flash the settings-reset UF2 to both devices once, then flash the normal UF2
files. Connect the dongle by USB and turn on the Q10. If it does not connect,
clear Bluetooth profiles on the Q10 and pair it again using the Q10's existing
Bluetooth-selection key.

The dongle hardware is based on
[`DZT970525/zmk_config_sofle_macintosch_dongle`](https://github.com/DZT970525/zmk_config_sofle_macintosch_dongle).
