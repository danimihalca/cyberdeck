# Cyberdeck POC

## Components

### SBC: Raspberry PI 4B

Currently running Raspberry OS.
To do:
- [x] Switch to Yocto Poky, template project https://github.com/danimihalca/yocto_rpi

### Display: ER-TFT3.95-1 display

Model: https://www.buydisplay.com/square-3-95-inch-720x720-ips-tft-lcd-display-rgb-interface

Reference:

- LT7680 controller
- NV3052C controller
- GT911 touch controller

#### ESP32 WROOM32 DevKitC 

Original code: https://www.buydisplay.com/download/ESP32/ER-TFT3.95-1_ESP32_Tutorial.zip

Wiring: same as in the original demo, plus D26 for blacklight

Build:

- original:
    - via **ArduinoIDE** with **esp32** board package, set for ESP32 Dev Module
    - may require reducing flash baudrate in case of failure
- Zephyr:
    - check dedicated [README.md](display/esp32/zephyr/README.md)


Demo:

<img src=res/PXL_20261028_082601478.jpg width="400">
<img src=res/PXL_20261028_082614191.jpg width="400">

#### Raspberry PI

DRM KMS driver for RaspberryPi OS: [README.md](display/rpi/drm_kms_driver/README.md)

Demo: 

<img src=res/PXL_20261030_181249473.jpg width="400">

To do:
- [x] Adapt for Yocto Poky


### Keyboard: BBQ20KBD

Hardware project: https://github.com/solderparty/bbq20kbd_hw

Firmware: https://github.com/solderparty/i2c_puppet

Raspberry PI linux driver: https://github.com/danimihalca/bbqX0kbd_driver

Sourced components and soldered.

Integration: https://youtube.com/shorts/A-UdpRkUM3E

To do:
- [x] Adapt for Yocto Poky


## Integration with Yocto

Source: [yocto_rpi template repository, branch cyberdeck](https://github.com/danimihalca/yocto_rpi/tree/cyberdeck)

Contains:

- display integration
- keyboard integration
- auto wifi connection with mDNS and SSH server
    
To do:
- [ ] update support (RAUC?)
- [ ] Improve wiring
- [ ] Integrate battery (BL-5C, 18650?)
- [ ] 3d printed case
