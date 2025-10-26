# Buildroot-Linux-for-Raspberry-Pi-3
This repository documents my process of building a minimal Linux image for Raspberry Pi 3 using **Buildroot**.  
The goal is to understand Linux system components like BusyBox, rootfs, and bootloaders through hands-on experimentation.

## 🧠 About
- Based on `raspberrypi3_defconfig`
- SSH enabled
- Custom kernel built with Buildroot
- Built and tested on Raspberry Pi 3

  ## 🛠 Build Steps
```bash
git clone https://github.com/buildroot/buildroot.git
cd buildroot
make raspberrypi3_defconfig
# Replace .config with this repo's config if desired
cp ../my-buildroot-rpi3/.config .
make
