---
layout: post
title: MQTT Client and Broker on Raspberry Pi
tags: mqtt raspberry-pi
---

### install Mosquitto Broker and Client
````bash
sudo apt install mosquitto mosquitto-clients
````

### subscribe to a topic
````bash
mosquitto_sub -h localhost -t "mqtt/test"
````

### publish to a topic
````bash
mosquitto_pub -h localhost -t "mqtt/test" -m "test"
````
