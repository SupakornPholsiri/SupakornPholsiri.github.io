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
```sh
node --version
npm --version
```
```sh
sudo mkdir /opt/zigbee2mqtt
sudo chown -R ${USER}: /opt/zigbee2mqtt
```
```sh
git clone --depth 1 https://github.com/Koenkk/zigbee2mqtt.git /opt/zigbee2mqtt
```
```sh
cd /opt/zigbee2mqtt
npm ci
```
