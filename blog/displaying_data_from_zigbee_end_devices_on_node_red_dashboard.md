---
layout: default
title: Displaying data from Zigbee end devices on Node-RED dashboard
description: Extracting sensor data from received JSON strings and display it on the Node-RED dashboard.
---

[<< Main page](https://supakornpholsiri.github.io/)

# Displaying data from Zigbee end devices on Node-RED dashboard

This blog covers the topic of extracting sensor data from received JSON strings and display it on the Node-RED dashboard. Please install both Node-RED and Zigbee2MQTT before reading further.

## Installing node-red-dashboard

Open your Node-RED frontend.

Click the button with three horizontal lines in the top right of your screen, then click **Manage pallette**.

![Manage pallette](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/manage_pallette.png)

Go to the install section and search for **node-red-dashboard**, then install **node-red-dashboard**.

![Installing node-red-dashboard](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/install_node_red_dashboard.png)

Now you can use the dashboard-related nodes to display data in your Node-RED frontend.

![Dashboard section](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/dashboard_nodes.png)

## Creating the Node-RED flow

After you run your Node-RED and go to you Node-RED frontend, you will be able to create your Node-RED flow.

The nodes that we will use to subscribe to the MQTT broker used by Zigbee2MQTT is the **mqtt in** nodes.

![MQTT in](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/MQTTin.png)

Then we are going to process the JSON recieved from the mqtt in nodes with the **function** nodes.

![Function](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/function.png)

Using the processed messages from the functions node, we can display them with the nodes in the dashboard section.

![Dashboard section](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/dashboard_nodes.png)

For the demonstration we are going to use a **notification** node to display information from a vibration sensor and a **gauge** node to display information from a light intensity sensor.

![Notification](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/notification.png)

![Gauge](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/gauge.png)

Connect each mqtt in node's output to the corresponding function node then connect the output of the function that connect to the vibration sensor to the notification node and connect the output of the function that connect to the light intensity sensor to the gauge node.

![Flow for displaying information from sensor](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/Flow.png)

### Setting up each mqtt in node's properties

![MQTT in's properties](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/mqtt_in_property.png)

Set the topic property to the same topic that the Zigbee end device uses to publish information to the MQTT broker, usually zigbee2mqtt/(The device's IEEE address)

Set the output property to JSON object.

Now we have to let Node-RED knows what MQTT server are we going to subscribe to. Do this by adding a new mqtt broker. \
After selecting the Add a new MQTT broker option, click the pencil button.

![Adding new MQTT broker](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Add_new_broker.png)

Set the server property to the server that hosts the MQTT broker.

![MQTT broker node's properties](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/MQTT_broker_node_property.png)

### Setting up each function node's properties

The **function1** node extracts the vibration's value from the JSON recieved from the vibration sensor.

![Vibration data](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/vibration_JSON.png)

![function1](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/function1.png)

The **function2** node extracts the illuminance_lux's value from the JSON recieved from the light intensity sensor.

![Illuminance data](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/light_JSON.png)

![function2](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/function2.png)

### Setting up gauge node's properties

![Gauge node's properties](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/gauge_property.png)

We have to create a group for the gauge. Do this by selecting the Add new dashboard group option, then press the pencil button.

![Dashboard group node](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/dashboard_group.png)

We also have to create a tab for the group. Do this be selecting the Add new dashboard tab option, then press the pencil button.

![Dashboard tab node](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/dashboard_tab.png)

### Setting up notification node's properties

![Notification node's properties](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/notification_property.png)

## Deploying the flow

After you finish editing your Node-RED flow, press the **Deploy** button located on the top right of your screen.

![Deploy](/assets/images/subscribe_to_zigbee2mqtt_with_node_red/Deploy.png)

Now you can go to your Node-RED dashboard at (Path to your Node-RED frontend)/ui/ .

![Dashboard UI 1](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/Dashboard_UI1.png)

![Dashboard UI 2](/assets/images/displaying_data_from_zigbee_end_devices_on_node_red_dashboard/Dashboard_UI2.png)