---
layout: default
title: Installing and Running Mosquitto broker using Docker.
description: Installing and Running Mosquitto broker using Docker in Linux.
---

[<< Main Page](https://supakornpholsiri.github.io/)

# Installing and Running Mosquitto broker using Docker.
In this blog, we will cover the topic of Installing Mosquitto broker and running it with a docker container. If you haven't installed docker, please follow the instructions in [this link](https://docs.docker.com/engine/install/ubuntu/) to download it.

## Preparing your mosquitto folder.
Before you run your Mosquitto broker docker container, you need to make a config file in your conputer for the Mosquitto broker to use.

Create a directory that will contain information about your Mosquitto broker.
```sh
$ mkdir mosquitto
```
Create subdirectories that will contain various informations about your Mosquitto broker in your directory.
```sh
$ mkdir mosquitto/data
$ mkdir mosquitto/config
$ mkdir mosquitto/log
```
Create the configuration file.
```sh
$ nano mosquitto/config/mosquitto.conf
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

## Installing and running your Mosquitto broker docker container.
Pull the Mosquitto docker image
```sh
sudo docker pull eclipse-mosquitto
```
Run the mosquitto broker
```sh
$ sudo docker run -it -p 1883:1883 -v [Path to your mosquitto configuration file]:/mosquitto/config/mosquitto.conf \
-v [Path to your mosquitto data directory]:/mosquitto/data -v [Path to your mosquitto log directory]:/mosquitto/log \
--name mosquitto eclipse-mosquitto
```
