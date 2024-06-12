---
layout: post
title: Disabling Raspberry Pi Internall Bluetooth Adapter 
tags: bluetooth raspberry-pi
---

edit /boot/config.txt
````bash
sudo nano /boot/config.txt
````

and add this at the bottom

````bash
# Disable internal Bluetooth adapter
dtoverlay=disable-bt
````
