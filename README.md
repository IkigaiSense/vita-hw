# Vita board

Notes on the build process of Vita board. Some pictures are [here](https://github.com/IkigaiSense/vita-hw/blob/master/vita-build.md).

- [ ] first prototype assembly
  - [x] BLE module soldering OK
  - [x] UF2 bootloader tested OK
  - [x] Accelerometer soldered
  - [x] Accelerometer tested 
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

The first prototype of Vita is based on an nRF52840 module from Raytac. The first prototype is manually assembled. It seems OK after flashing the UF2 bootloader to it with BMP.

## Vita Firmware

Vita may use FreeRTOS or Zephyr for firmware development.

## Vita Software

Vita itself is a sensor hub. It requires a smart phone or tablet to do further processing and possible data transfer at the user's explicit consent. The user decide who and when to share his or her own health data.

So the mobile application has to be developed.

## Certifications 


