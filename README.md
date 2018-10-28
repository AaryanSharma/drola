﻿# Drola
A Drone Monitoring System using LORA

We have introduced a seperate Hardware unit for drones which can easily mount on any kind of commercial or non-commercial drones. DroLa End node consists of a GPS module, microcontroller, LoRa module and a separate battery.

### Setting up Drola End Node
Setup the units according to the schematics given in the `LoRa_End_Node`. The end node microcontroller should contain the given firmware. Communication channel and addresses of Lora modules should be according to the given firmware.

### Setting up Drola Web
1) Clone the repository at the Base station. 
2) Run the following command to install the node module dependencies.
   ```
   cd Drola_Base_Node
   npm install
   ```
2) Connect the configured base station Lora module to the base station computer. You can start the node server by running following command-
   ```
   npm start
   ```
3) Start the Websocket server and Websocket client to see the end node locations in the browser application
   ```
   cd Drola_Base_Node/api
   python `socket_server.py`
   python `read_serial.py`
   ```
4) Go to http://localhost:3000/ in your browser to see all the locations of the Live End Nodes.

**Note:** You can test the API by running `socket_client.py` instead of `read_serial.py`. It will show you some hard-coded locations. Trusted zones are not implemented yet to protect AES keys. The keys are hardcoded in this version.
  
## Base Node Application
![Base Node App](/Drola_Base_Node/Drola_snap_4.png?raw=true "Base Node App")

## DroLa End Node
![End Node](/LoRa_End_Node/Drola_end_node.jpg?raw=true "Drole End Node")
<hr>

For more information please refer to the [Wiki](https://github.com/NamalJayasuriya/drola/wiki/Drola) page.
