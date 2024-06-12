---
layout: post
title: Installing npm and Node.js on Raspberry Pi
tags: node.js npm raspberry-pi
---

### install nvm (Node Version Manager)
````bash
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
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
