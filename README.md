# lcdshow2026
Modern CLI install packages for those raspi covers that came with LCD's.

THIS IS VERY EARLY ALPHA. RUN AT YOUR OWN RISK
# lcdshow2026

A modern, safe, auto-detecting replacement for the legacy `LCD-show` scripts used
with 3.5" SPI TFT displays on Raspberry Pi OS Bookworm and Debian Trixie. 

This project is maintained by **mpzsol**. The code itself is from the wayland port repository by caliston (unaffiliated, honestly just pulled this together from an llm to see if it works from my CLI)

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

