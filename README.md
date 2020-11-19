# IR01
Using the IR01 as an OpenOCD SWD programmer for supported XinaBox Cores

## Install OpenOCD
Follow Adafruit's excellent indstructions found [here](https://learn.adafruit.com/programming-microcontrollers-using-openocd-on-raspberry-pi?view=all), until the point saying `That's pretty much it!`
There might be a simpler way, and if so, please post a pull request.

## Prepare OpenOCD for IR01
1. Change the SWD pin numbers: `sudo nano /usr/local/share/openocd/scripts/interface/raspberrypi2-native.cfg`
1. Find `bcm2835gpio_swd_nums` and change to `bcm2835gpio_swd_nums 11 8`
1. Find and uncomment `bcm2835gpio_srst_num` and change to `bcm2835gpio_srst_num 4`
1. Exit: `^x`

## Flash bootloader to CS11
1. Create a suitable folder: `cd ~` -> `mkdir bootloaders` -> `cd bootloaders`
1. Download the CS11 Bootloader: `wget https://github.com/xinabox/XinaBox-Bootloaders/raw/master/CS11/cs11_bootloader.bin` 
1. Download the CS11 Config file: `wget https://raw.githubusercontent.com/xinabox/XinaBox-Bootloaders/master/CS11/openocd.cfg`
1. 
