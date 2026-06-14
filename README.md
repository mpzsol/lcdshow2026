# lcdshow2026
Modern CLI install packages for those raspi covers that came with LCD's.

THIS IS VERY EARLY ALPHA. RUN AT YOUR OWN RISK
# lcdshow2026

A modern, safe, auto-detecting replacement for the legacy `LCD-show` scripts used
with 3.5" SPI TFT displays on Raspberry Pi OS Bookworm and Debian Trixie. 

This project is maintained by **mpzsol**. The code itself is from the wayland port repository by caliston (unaffiliated, honestly just pulled this together from an llm to see if it works from my CLI)

What it does

Detects:

Boot config path: /boot/config.txt or /boot/firmware/config.txt

Kernel version: disables KMS on 6.x+ for SPI LCDs

LCD controller: ILI9486, ILI9341, HX8357D, ST7789 (via dmesg)

Touchscreen: ADS7846 / XPT2046 (via dmesg)

Downloads the correct Device Tree overlay

Safely appends a small block to config.txt

Adds a basic X11 touchscreen calibration file


## Features

- Auto-detects LCD controller:
  - ILI9486
  - ILI9341
  - HX8357D
  - ST7789
- Auto-detects touchscreen controller:
  - ADS7846
  - XPT2046
- Auto-detects boot layout:
  - `/boot/config.txt`
  - `/boot/firmware/config.txt`
- Auto-detects kernel version and disables KMS when required
- Installs correct Device Tree overlay
- Safe config patching (no destructive overwrites)
- Touchscreen calibration support
- Clean uninstall script

## Install

## Install

```bash
git clone https://github.com/mpzsol/lcdshow2026.git
cd lcdshow2026
chmod +x LCD35-show LCD35-uninstall
sudo ./LCD35-show

** reboot here
sudo reboot

## Uninstall

cd LCD35-modern
sudo ./LCD35-uninstall
sudo reboot
```

Notes
Designed for SPI 3.5" TFTs wired like common Waveshare/GoodTFT boards.

If auto-detection fails, it defaults to ILI9486 (waveshare35a overlay).

You can tweak resolution/refresh in the hdmi_cvt line if needed.
