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
### Installing the docker container
Pull the Mosquitto docker image
```sh
$ sudo docker pull eclipse-mosquitto
```
![Pulling Mosquitto image](/assets/images/DockerPullMosquitto.png)

### Running the docker container
Run the mosquitto broker
```sh
$ sudo docker run -it -p 1883:1883 -v [Path to your mosquitto configuration file]:/mosquitto/config/mosquitto.conf \
-v [Path to your mosquitto data directory]:/mosquitto/data -v [Path to your mosquitto log directory]:/mosquitto/log \
--name mosquitto eclipse-mosquitto
```
![Mosquitto Running](/assets/images/MosquittoDocker.png)
You can terminate the session by pressing Ctrl+c.

The mosquitto docker container stays in your system and can be use again with the command below. Don't worry about not seeing any output beside the container's name this time, it's working.
```sh
$ sudo docker start mosquitto
```

This time, Terminate the session with
```sh
$ sudo docker stop mosquitto
```

If you don't want to keep the docker container in your system you can use this command to remove the container.
```sh
$ sudo docker rm mosquitto
```

### Using the mosquitto broker docker container
We have covered how to run the docker container, but how do you test if the broker is actually working? By connecting a client to your broker of course!

Before we can connect our clients to the broker we have to know the IP of the computer that is hosting it first. \
We can check our IP using 
```sh
$ ifconfig
```
![Checking IP address]()

After that connect your client via a GUI-based MQTT client or the mosquitto package. I will use a GUI-based MQTT client for the demonstration.
![MQTT Explorer]()

If you're running the container in a VM, make sure to use bridged network connection. Otherwise, any client that is not the VM itself won't be able to connect to your broker.