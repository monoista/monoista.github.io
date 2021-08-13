---
layout: post
title: CouchDB and Raspberry Pi
tags: couchdb raspberry-pi
---

### install all necessary dependencies
````bash
sudo apt-get --no-install-recommends -y install \
     build-essential pkg-config erlang \
     libicu-dev libmozjs185-dev libcurl4-openssl-dev
````

### download CouchDB source
````bash
wget https://www.apache.org/dyn/closer.lua?path=/couchdb/source/3.1.1/apache-couchdb-3.1.1.tar.gz
````

### configure installation
````bash
./configure
````

### build CouchDB
````bash
make release
````

### create couchdb user and its home directory
````bash
sudo useradd -d /home/couchdb couchdb
sudo mkdir /home/couchdb
sudo chown couchdb:couchdb /home/couchdb
````

### copy build into /home/couchdb directory
````bash
cd ./rel/couchdb/
sudo cp -Rp * /home/couchdb
sudo chown -R couchdb:couchdb /home/couchdb
````

### update permission of ini files
````bash
sudo chmod 0644 /home/couchdb/etc/*
````

### start CouchDB server
````bash
sudo -i -u couchdb /home/couchdb/bin/couchdb
````

### edit local.ini for accessing CouchDB from other external IP address
````bash
sudo nano /home/couchdb/etc/local.ini
````
change line
````bash
#bind_address = 127.0.0.1
````
to
````bash
bind_address = 0.0.0.0
````
and restart CoachDB server

### check that CouchDB is running
````bash
http://127.0.0.1:5984/_utils/index.html
````

### running CouchDB on boot
````bash
sudo mkdir /var/log/couchdb/
sudo chown couchdb:couchdb /var/log/couchdb
````
go to http://127.0.0.1:5984/_utils/#/_config
select + Add Options
set
log for Section,
file for Name and
/var/log/couchdb/couch.log for Value.

### create the systemd service
````bash
sudo nano /lib/systemd/system/couchdb.service
````

````
[Unit]
Description=CouchDB Service
After=network.target
  
[Service]
Type=idle
User=couchdb
Restart=always
ExecStart=/home/couchdb/bin/couchdb
  
[Install]
WantedBy=default.target
````

set permissions
````
sudo chmod 644 /lib/systemd/system/couchdb.service
````

````
sudo systemctl daemon-reload
sudo systemctl enable couchdb.service
````
