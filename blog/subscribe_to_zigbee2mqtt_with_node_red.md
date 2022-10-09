---
layout: default
title: Subscribing to Zigbee2MQTT with Node-RED
description: Create a Node-RED flow to subscribe messages to the MQTT broker used by Zigbee2MQTT.
---

[<< Main page](https://supakornpholsiri.github.io/)

# Subscribing to Zigbee2MQTT with Node-RED

This blog will cover the topic of Creating a Node-RED flow to subscribe messages to the MQTT broker used by Zigbee2MQTT. Please install both Node-RED and Zigbee2MQTT before reading further.

## Creating the Node-RED flow

After you run your Node-RED and go to you Node-RED frontend, you will be able to create your Node-RED flow.

The nodes that we will use to subscribe to the MQTT broker used by Zigbee2MQTT is the **mqtt in** nodes.

![MQTT in](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/MQTTin.png)

Then we are going to look at the messages recieved from the nodes with the **debug** nodes.

![Debug](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Debug.png)

Connect the mqtt in node's output to a Debug node to view the massage recieved from the MQTT broker.

![Node-RED's frontend](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Node_RED_frontend.png)

### Setting up each mqtt in node's properties

![MQTT in's properties](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/mqtt_in_property.png)

Set the topic property to the same topic that the Zigbee end device uses to publish information to the MQTT broker, usually zigbee2mqtt/(The device's IEEE address)

Set the output property to any option base on what you need to do with the output.

Now we have to let Node-RED knows what MQTT server are we going to subscribe to. Do this by adding a new mqtt broker. \
After selecting the Add a new MQTT broker option, click the pencil button.

![Adding new MQTT broker](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Add_new_broker.png)

Set the server property to the server that hosts the MQTT broker.

![MQTT broker node's properties](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/MQTT_broker_node_property.png)

### Setting up each debug node's properties

You can either see the whole msg object or its payload. The information we want to see is in the payload.

![Debug node's properties](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/debug_property.png)

## Deploying the flow

After you finish editing your Node-RED flow, press the **Deploy** button located on the top right of your screen.

![Deploy](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Deploy.png)

Now you can see the messages the Zigbee end device publish to the MQTT broker in your debug window.

![The flow in action](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Deployed.png)