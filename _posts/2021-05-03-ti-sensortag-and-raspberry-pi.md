---
layout: post
title: TI SensorTag and Raspberry Pi
tags: raspberry-pi sensortag
---

### confirm that bluetooth service is running
````bash
sudo service bluetooth status
````

### scan for BLE devices
````bash
sudo hcitool lescan
````

{% highlight console %}
[MAC address] (unknown)
[MAC address] (unknown)
[MAC address] CC2650 SensorTag
[MAC address] (unknown)
[MAC address] (unknown)
{% endhighlight %}

### install [bluepy - Python interface to BLE](https://github.com/IanHarvey/bluepy)
````bash
sudo apt-get install libglib2.0-dev
cd Development
git clone https://github.com/IanHarvey/bluepy.git
cd bluepy/bluepy
sudo pip install bluepy
````

### get all sensor data from SensorTag
````bash
python sensortag.py [MAC address] --all
````
