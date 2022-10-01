---
layout: default
title: Installing and Running Mosquitto broker using Docker.
description: Installing and Running Mosquitto broker using Docker in Linux.
---

[<< Main Page](https://supakornpholsiri.github.io/)

# Installing and Running Mosquitto broker using Docker.
In this blog, we will cover the topic of Installing Mosquitto broker and running it with a docker container. If you haven't installed docker, please follow the instructions in [this link](https://docs.docker.com/engine/install/ubuntu/) to download it.

## Preparing your mosquitto folder.
Before you run your Mosquitto broker docker container, you need to make a config file in your conputer for the Mosquitto broker to use. \

1. Create a directory that will contain information about your Mosquitto broker.
```sh
mkdir mosquitto
```
2. Create subdirectories that will contain various informations about your Mosquitto broker in your directory.
```sh
mkdir mosquitto/data
mkdir mosquitto/config
mkdir mosquitto/log
```
3. Create the configuration file.
```sh
nano mosquitto/config/mosquitto.conf
```
This is an example of how a configuration file should look like.
```sh
listener 1883
allow_anonymous true

persistence true
persistence_location /mosquitto/data

log_dest file /mosquitto/log/mosquitto.log
log_dest stdout
```
