# lcdshow2026
Modern CLI install packages for those raspi covers that came with LCD's.

THIS IS VERY EARLY ALPHA. RUN AT YOUR OWN RISK

A modern, safe, auto-detecting replacement for the legacy `LCD-show` scripts used
with 3.5" SPI TFT displays on Raspberry Pi OS Bookworm and Debian Trixie. 

This project is maintained by **mpzsol**. The code itself is from the wayland port repository by caliston (unaffiliated, honestly just did this after an llm found calistons work to go on)

## Features

- Auto-detects LCD controller:
  - ILI9486, ILI9341, HX8357D, ST7789
- Auto-detects touchscreen controller:
  - ADS7846, XPT2046
- Auto-detects boot layout:
  - `/boot/config.txt` or `/boot/firmware/config.txt`
- Auto-detects kernel version (disables KMS when required)
- Rotation support:
  - `0`, `90`, `180`, `270`
  - Auto-rotation heuristic
- Touchscreen calibration wizard
- Safe config patching
- Clean uninstall script

## Install

```bash

git clone https://github.com/mpzsol/lcdshow2026.git
cd lcdshow2026
chmod +x LCD35-show LCD35-uninstall calibrate-touchscreen
sudo ./LCD35-show
sudo reboot
```
## Rotation
```

sudo ./LCD35-show 0
sudo ./LCD35-show 90
sudo ./LCD35-show 180
sudo ./LCD35-show 270

If no rotation is specified, auto-rotation is attempted.
```

## Touchscreen Calibration Wizard
```

sudo ./calibrate-touchscreen

If missing:

sudo apt install xinput-calibrator

## Uninstall / Restore HDMI

sudo ./LCD35-uninstall
sudo reboot

```
## Supported Systems

- Raspberry Pi OS Bookworm
- Debian Trixie ARM
- Kernel 5.x, 6.x, 6.6 LTS, 6.8+

## License

None. Thanks /caliston/ for making the waveland port.

## Starving Scripter

Accepting donations at mpzsol on cashapp and venmo if you realize how much time this just saved you in 2026. 
