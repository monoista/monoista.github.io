---
layout: post
title: Updating npm and Node.js on Raspberry Pi
tags: node.js npm raspberry-pi
---

### update npm
````bash
sudo npm install -g npm@latest
````

### update Node.js
````bash
nvm ls
nvm ls-remote
nvm install [version.number]
````

### select Node.js version
````bash
nvm use [version.number]
````
