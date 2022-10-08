---
layout: default
title: Subscribing to Zigbee2MQTT with Node-RED
description: Create a Node-RED flow to subscribe messages to the MQTT broker used by Zigbee2MQTT.
---

[<< Main page](https://supakornpholsiri.github.io/)

# Subscribing to Zigbee2MQTT with Node-RED

This blog will cover the topic of Creating a Node-RED flow to subscribe messages to the MQTT broker used by Zigbee2MQTT. Please install both Node-RED and Zigbee2MQTT before reading further.

# Creating the Node-RED flow

After you run your Node-RED and go to you Node-RED frontend, you will be able to create your Node-RED flow.



The nodes that we will use to subscribe to the MQTT broker used by Zigbee2MQTT is the **MQTT in** node.



Connect the MQTT in node's output to a Debug node to view the massage recieved from the MQTT broker.
