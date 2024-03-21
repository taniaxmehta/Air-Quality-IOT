# Air-Quality-IOT
IoT Server on Raspberry Pi via Arduino Uno for Air Quality, Temperature, Humidity Data

# Concept
This projects sets up an internet of things server on your Raspberry Pi. The server uses Mosquitto MQTT, InfluxDB, Node-RED, Graphana in docker containers. It leverages IoTStack tool which configured the docker containers. Through the Arduino Uno you can collect any kind of sensor data, send it over your network to this raspberry pi server. The project will visualise it on a Grafana dashboard.

This system consists of a series of sensor nodes that send sensor data in a JSON message over the network to a Raspberry Pi via MQTT.

MQTT is a network protocol where a client pushes data to a broker, such as mosquitto, and the broker pushes that data to any client that has subscribed to that topic. A topic categorises the data that is sent. 

Any client that is subscribed to home slash sensor will be forwarded this MQTT message.

NodeRED will subscribe to this topic, interpret the json message data and then send the data to a database to be stored and used. InfluxDB will store all the sensor data.

Then a Graphana front end will query the database in order to display the data we want to see and do a whole host of other things.

# Hardware
* Raspberry Pi 4 (Raspbian OS 64)
* Arduino Uno

