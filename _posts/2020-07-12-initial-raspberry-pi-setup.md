---
layout: post
title: Initial Raspberry Pi Setup
tags: raspberry-pi
---

### [update Raspberry Pi packages](https://www.raspberrypi.org/documentation/raspbian/updating.md)
````bash
sudo apt update
sudo apt full-upgrade
````

### install display drivers and rotate the display by 270 degrees (counterclockwise)
````bash
mkdir Development
cd Development
git clone https://github.com/goodtft/LCD-show.git
cd LCD-show/
sudo ./LCD35-show 270
````
or this repository if the display remains white
````bash
git clone https://github.com/MrYacha/LCD-show.git
````

### rotate the display (counterclockwise)
````bash
sudo ./rotate.sh 270
````

### callibrate the display
````bash
cd LCD-show/
sudo dpkg -i -B xinput-calibrator_0.7.5-1_armhf.deb
````
