# Vita board

Notes about the build of Vita board.

## Vita Hardware

Vita is based a nRF52840 module by Raytac. The first prototype is manual assembled. It seems OK after flashing the UF2 bootloader to it with BMP.

## Adafruit nRF bootloader

This is a UF2 bootloader. Still have to understand some details. The build is OK.

### build ikigaisense_vita

```
make BOARD=ikigaisense_vita all
```

###flash the bootloader with JLink

```
make BOARD=ikigaisense_vita flash
```

### flash SoftDevice (and chip erase):

```
make BOARD=ikigaisense_vita sd
```

