---
layout: post
title: Securing Raspberry Pi
tags: fail2ban security raspberry-pi
---

### install Fail2Ban
````bash
sudo apt install fail2ban
````

### change default settings
````bash
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
sudo nano /etc/fail2ban/jail.local
````

### restart service
````bash
sudo service fail2ban restart
````

### check status
````bash
sudo fail2ban-client status
````
or
````bash
sudo fail2ban-client status sshd
````
