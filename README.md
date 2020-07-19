# Vita board

Ikigai is something worthy of doing. 
You start from small. 
You get better after mistake and practice.
When you do it, you enjoy doing it. 

Notes on the build process of Vita board. Some pictures are [here](https://github.com/IkigaiSense/vita-hw/blob/master/vita-build.md).

- [ ] first prototype assembly
  - [x] BLE module soldering OK
  - [x] UF2 bootloader tested OK
  - [ ] Accelerometer soldered
  - [ ] Accelerometer tested 
  - [ ] CircuitPython is built and loaded
  - [ ] daughter board assembly
  - [ ] daughter board preliminary test
  - [ ] build/load zephyr for nRF52840
- [ ] what to change for the second prototype   
  - [ ] what rechargeable battery to add
  - [ ] nRF52840 is able to handle the computation
  - [ ] what are other options, wireless link, algo, and hw?
- [ ] patch design and hardware changes
- [ ] iOS app development
- [ ] android app development
- [ ] integration test

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

