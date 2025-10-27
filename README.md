# Buildroot-Custom-Linux-for-Raspberry-Pi-3
This repository documents my process of building a minimal Linux image for Raspberry Pi 3 using **Buildroot**.  
The goal is to understand Linux system components like BusyBox, rootfs, and bootloaders through hands-on experimentation.

The system includes:
- A minimal Linux kernel  
- BusyBox utilities  
- SSH (Dropbear) for remote access  
- Basic networking setup

##  Project Details

| Item | Description |
|------|--------------|
| **Target Board** | Raspberry Pi 3 |
| **Build System** | Buildroot |
| **Filesystem Type** | ext4 |
| **Default Config Used** | `raspberrypi3_defconfig` |
| **Access Method** | SSH / Serial Console |

## Boot Flow 
 **Power On** ⇨ **Bootloader** (loads kernel +dtb)  ⇨ **Kernel** (initiates hardware) ⇨ **Mounts** (rootfs) ⇨ **Runs** (BusyBox) ⇨ **You get a shell** 

## Installation Steps

### Install Prerequisites
```sh
sudo apt update
sudo apt install which sed make binutils build-essential \ diffutils gcc g++ bash patch gzip bzip2 perl tar cpio \ unzip rsync file bc findutils wget python3 libncurses5-dev \ libncursesw5-dev git
```
### Download Buildroot
```sh
git clone https://gitlab.c make raspberrypi3_defconfiom/buildroot.org/buildroot.git
```
### Select the Board
```sh
  make raspberrypi3_defconfig
```
### Customize the Build
```sh
  make menuconfig
  make linux-menuconfig
  make busybox-menuconfig
```
### Build the system
```sh
  make
```  


