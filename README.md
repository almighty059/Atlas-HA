# Atlas-HA

## Table of Contents

- [Introduction](#introduction)
- [RPi Installation](#rpi-installation)
- [HA Installation](#ha-installation) 

## Introduction
This repository is designed to assist those who want to use Atlas EZO sensors connected to a Raspberry Pi (RPi) with Home Assistant, without relying on the Atlas IoT software. It provides access to all available commands for each sensor.

## RPi-Installation
To prepare your RPi open a terminal window and execute the following commands.

1. Update and Upgrade the System:  
   Start by updating and upgrading the system to ensure all packages are up to date.
```
sudo apt update
sudo apt upgrade
```

2. Install MQTT Broker (Mosquitto):  
   Mosquitto is a popular MQTT broker that you can install on your Raspberry Pi.
```
sudo apt install mosquitto mosquitto-clients
```

3. Enable and Start the Mosquitto Service:  
   Enable the Mosquitto service to start on boot and start it immediately.
```
sudo systemctl enable mosquitto
sudo systemctl start mosquitto
```

4. Install Python and PIP:  
   Ensure you have Python and PIP installed to run your MQTT scripts.
```
sudo apt install python3 python3-pip
```

5. Install the Paho-MQTT Library:  
   Paho-MQTT is a Python library for implementing MQTT clients.
```
pip3 install paho-mqtt
```

## HA-Installation

1. Install Mosquitto in Home Assistant  
   Step 1: In the HA sidebar, click Settings. Under Settings, select Add-ons.  
   Step 2: Ue the search bar at the top of the Add-on Store to search for "Mosquitto" and select it.  
   Step 3: Click the Install button on the Mosquitto broker page. Wait for the installation to complete.  
   
2. Create a User in Home Assistant  
   Step 1: In the sidebar, go to Settings > People. Select the Users tab at the top. Click the Add User button.  
   Step 2: Fill in the following details:  
   Name: A descriptive name for the MQTT user (e.g., "mqtt_user").  
   Username: Enter a username (e.g., "mqttuser").  
   Password: Set a strong password for the user.  
   Make sure the Admin option is not enabled for this user (best practice for MQTT-specific users).  
   Click Create to add the user.  
   
3. Configure Mosquitto Add-on  
   Step 1: Go back to the Add-ons page and select the Mosquitto broker add-on.  
   Navigate to the Configuration tab and ensure the configuration uses the user you just created:  
   Copy code.  
   ```   
   logins:
     - username: mqttuser
       password: yourpassword
   anonymous: false
   customize:
     active: true
     folder: mosquitto
   ```
   Step 2: Replace mqttuser and yourpassword with the credentials you created.  
   Step 3: Save the configuration.  
   Step 4: Go to the Info tab of the Mosquitto add-on. Click Start to run the broker.  
   
4. Configure MQTT Integration in Home Assistant  
   Step 1: Go to Settings > Devices & Services. Click Add Integration. Search for and select MQTT.  
   Step 2: In the configuration dialog: Use the Host as localhost or the IP address of your Home Assistant. Enter the username and password. Click Submit.

