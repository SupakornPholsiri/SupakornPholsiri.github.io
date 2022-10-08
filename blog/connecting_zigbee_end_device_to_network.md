---
layout: default
title: Connecting Zigbee end devices to Zigbee network
description: Use a ZigBee Coordinator USB dongle and connect/join ZigBee end devices to the Zigbee network.
---

[<< Main Page](https://supakornpholsiri.github.io/)

# Connecting Zigbee end devices to Zigbee network

This blog with cover how to use a ZigBee Coordinator USB dongle and connect/join ZigBee end devices to the Zigbee network. If you haven't installed Zigbee2MQTT yet, please follow the instructions in [this blog](https://supakornpholsiri.github.io/blog/installing_zigbee2mqtt_on_linux.html) first.

## Editing the Zigbee2MQTT configuration file

Open the configuration file

```sh
$ nano /opt/zigbee2mqtt/data/configuration.yaml
```

Edit the configuration file

```sh
homeassistant: false
permit_join: true
mqtt:
  base_topic: zigbee2mqtt
  # specify the IP address or hostname of your MQTT broker
  server: 'mqtt://localhost:1883'
  # MQTT server authentication, uncomment if required:
  #user: xxxx
  #password: xxxx
serial:
  # specify the serial COM port (The location that the Zigbee-Adapter mounted on.)
  port: /dev/ttyUSB0
advanced:
  # specify the ZigBee channel number
  channel: 15
frontend:
  # enable Web front-end for Zigbee2MQTT on port 8080 (localhost:8080)
  port: 8080  
```

Set **permit_true** to true when you want to connect new zigbee end devices to the zigbee network. Set it to false otherwise.

## Connecting devices to the network

Start Zigbee2MQTT

![Zigbee2MQTT](/assets/images/installing_zigbee2mqtt_on_linux/Zigbee2MQTT_started.png)

Connect the device to the network. For example, Xiaomi MiJia temperature and humidity sensor (WSDCGQ01LM) can be connect to the network by holding the button on the side of the device for around 5 seconds.

<img src = "./assets/images/connecting_zigbee_end_device_to_network.md/Zigbee_device.jpg" width = "50"/>

![Xiaomi MiJia temperature and humidity sensor](/assets/images/connecting_zigbee_end_device_to_network.md/Zigbee_device.jpg) ![Device connected](/assets/images/connecting_zigbee_end_device_to_network.md/Device_connected.jpg)

Once connected, the output will notify that a new device has been connected.

After that you can recieve the infomation from the device in your output in JSON string format.

You can also see the infomation about the connected devices in your Zigbee2MQTT frontend.
