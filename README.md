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
sudo apt-get install python3-paho-mqtt
```

5. Install the SMBus2 Module:    
   A Python 3 module that provides bindings for the SMBus interface, which is commonly used for I2C communication.
```
sudo apt-get install python3-smbus2
```

## HA-Installation

1. Install Mosquitto in Home Assistant  
   Step 1: In the HA sidebar, click Settings. Under Settings, select Add-ons.  
   Step 2: Ue the search bar at the top of the Add-on Store to search for "Mosquitto" and select it.  
   Step 3: Click the Install button on the Mosquitto broker page. Wait for the installation to complete.  
   
2. Click on the add-on's Documentation tab for further installation instructions.  



   
