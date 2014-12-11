Pi Word Clock
==============

My 7 and 8yr old kids wanted to get started with electronics and programming,
 so we started off with an LED word clock.

Code & Images for making Word Clocks included. We used Raspberry Pi and 8x8 matrix.
Code is Python & will possibly add a C version.
Staring with an Adafruit LED backpack via I2C may support others soon.

https://learn.adafruit.com/adafruit-led-backpack/overview

You can buy transparency paper for inkjet printers but even regular printer paper
works quite well.

To get i2c working on our pi we did the following

```bash
sudo nano /etc/modules
```

uncomment (remove #) or add these lines to the end of /etc/modules

```
i2c-dev
snd-bcm2835
```

If you have this file, it needs editing

```bash
sudo nano /etc/modprobe.d/raspi-blacklist.conf
```

Then comment out (add # to the start) or remove

```
#blacklist i2c-bcm2708
```

Reboot
```bash
sudo reboot
```

```bash
sudo apt-get install python-smbus
sudo apt-get install i2c-tools
```
Hook up your backpack to the pi and type

```bash
sudo i2cdetect -y 1
```

We had an old 256MB Pi Model B so we typed

```bash
sudo i2cdetect -y 0
```

This will show the I2C address your backpack(s) are using

