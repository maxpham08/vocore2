# Compile Example

make -C /Volumes/OpenWrt/vocore2/build_dir/target-mipsel_24kc_musl/linux-ramips_mt76x8/linux-4.14.131 M=$PWD CROSS_COMPILE="/Volumes/OpenWrt/vocore2/staging_dir/toolchain-mipsel_24kc_gcc-7.3.0_musl/bin/mipsel-openwrt-linux-" ARCH="mips" modules

ili9806 is for old version screen(back mark is 'vocore2', it is big endina which is good for 24bit color)
nt35510 is for new version screen(back mark is 'djn1522', it is little endina which is good for 16bit color/framebuffer)

because framebuffer only support 16bit or 32bit color, so it is very slow to convert data from 32bit to 24bit or from 16bit to 24bit, new version solve this problem.
If you want better colors, need to use libusb send data to the screen, and make it in R-G-B-R-G-B... order. R,G,B each takes one byte.

# Bin File

- fbusb.vocore2.ko is for the screen back marked 'VoCore'
- fbusb.djn1522.ko is for the screen back marked 'djn1522'

The two screens are using different driver chip, so we need to seprated the driver.

# Copyright

fbusb driver belongs to Vonger Elec & Tech Co.Ltd, DO NOT allowed for commercial usage.
