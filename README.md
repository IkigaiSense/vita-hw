# Vita board

Notes about the build of Vita board.

## Vita Hardware

Vita is based on an nRF52840 module from Raytac. The first prototype is manually assembled. It seems OK after flashing the UF2 bootloader to it with BMP.

## Adafruit nRF bootloader

### Clone the repo

```
git clone https://github.com/adafruit/Adafruit_nRF52_Bootloader
cd Adafruit_nRF52_Bootloader
git submodule update --init
```

This is a UF2 bootloader. Still have to understand some details. The build is OK.

* DFU over serial and OTA (app, bootloader+SoftDevice)
* Self-upgradable via seial and OTA
* DFU using UF2 for app

### build ikigaisense_vita

```
make BOARD=ikigaisense_vita all
```

### flash the bootloader with JLink

```
make BOARD=ikigaisense_vita flash
```

### flash SoftDevice (and chip erase):

```
make BOARD=ikigaisense_vita sd
```

## Reference

To set up the build environment, at least you have to build Adafruit nRF Utility and make it available in your PATH. Python3 is required. Then you may need NordicSemi nrfprog.

```
~/Adafruit_nRF52_nrfutil/nordicsemi/dist
```

The above is usually where you can find the executable of ```adanrfutil```.

ARM GNU toolchain is as follows.

```
~/gcc-arm-none-eabi-8-2018-q4-major/bin
```

