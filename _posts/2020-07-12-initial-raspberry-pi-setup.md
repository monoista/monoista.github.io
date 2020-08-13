---
layout: post
title: Initial Raspberry Pi Setup
tags: raspberry-pi
---

### update Raspberry Pi packages
````bash
sudo apt update
sudo apt upgrade
````

### install display drivers
````bash
mkdir Development
cd Development
git clone https://github.com/goodtft/LCD-show.git
cd LCD-show/
sudo ./LCD35-show
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
