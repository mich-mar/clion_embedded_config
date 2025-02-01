# STM32 in Clion envaiorment

## Introduction
I recommend opening that guide in CLion, which allows you to click on 
commands and run them automatically for you. This guide is based on a tutorial by 
Eka Susilo (https://www.youtube.com/watch?v=FNDp1G0bYoU).
Any issues encountered during installation were resolved with the help of this GitHub 
guide (https://github.com/riscv-collab/riscv-openocd/issues/970).

## Step-by-step Guide

### 1. Update and upgrade your system

```bash
    sudo apt-get update
```

```bash
    sudo apt-get upgrade
```

### 2. Dowland essential software
```bash
    sudo apt-get install git build-essential gcc-arm-none-eabi libtool libusb-1.0-0-dev gdb-multiarch
```

### 3. Reboot your system

### 4. Dowland newer version of openOCD
```bash
 git clone https://github.com/openocd-org/openocd
```

### 5. Build openOCD
```bash
cd openocd/
```
```bash
./bootstrap
```

```bash
./configure --prefix=/usr/local --enable-ftdi --enable-stlink --enable-jlink
```
```bash
make
```
```bash
sudo make install
```
During the installation process, you may encounter the following problem:
```bash
configure: error: libjaylink-0.2 is required for the SEGGER J-Link Programmer
```
In that case, you have to compile the libjaylink by yourself (openocd/src/jtag/drivers/libjaylink).

### 6. Check version of installed openOCD
```bash
openocd -v
```

### 7. Check path to openOCD
```bash
which openocd
```

### 8. Last step is to link our Clion envaiorment with openOCD and STM32MX.
Follow guide on official Clion site (https://www.jetbrains.com/help/clion/embedded-development.html). Obviously skip steps with installing openOCD and toolchains.
