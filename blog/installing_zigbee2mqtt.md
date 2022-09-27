---
layout: default
title: Installing Zigbee2MQTT
description: Installing Zigbee2MQTT on Linux.
---

Set up Node.js repository.
```sh
sudo curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
```
Install Node.js and required dependencies
```sh
sudo apt-get install -y nodejs git make g++ gcc
```
Verify that the correct nodejs and npm versions have been installed.
```sh
node --version
npm --version
```
![Correct version example](/assets/images/CorrectVersionExample.png)
nodejs version should be v14.X, V16.x, V17.x or V18.X.
npm version should be 6.X, 7.X or 8.X
Create a directory for zigbee2mqtt and set your user as owner of it.
```sh
sudo mkdir /opt/zigbee2mqtt
sudo chown -R ${USER}: /opt/zigbee2mqtt
```
Clone Zigbee2MQTT repository.
```sh
git clone --depth 1 https://github.com/Koenkk/zigbee2mqtt.git /opt/zigbee2mqtt
```
Install dependencies as your user.
```sh
cd /opt/zigbee2mqtt
npm ci
```
