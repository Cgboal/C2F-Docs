---
description: 'Download here: https://github.com/Cgboal/C2-SDK'
---

# C2-SDK

### Introduction 

The C2-SDK is a Python package designed to be used inside Docker containers to send data back to the Master Node. The C2-SDK also makes available environment variables passed to the Docker container by the Agent. 

### Installation

Clone the C2-SDK [repository](https://github.com/Cgboal/C2-SDK) and then run `python setup.py install.`

### c2sdk.rest

This Python module includes classes used to perform API calls to the Master Node.

#### c2sdk.rest.Rester\(\)

Rester is a class which handles rest calls to the master node. It has the following methods. 

* Rester.post\(table, data\) The table parameter is the name of the table the Module is posting data to, as defined within the Module File described in the previous section. The data parameter is a dictionary, with the keys being the database table columns, and the values being the values to insert into those columns. See the Example Module section for examples.

### c2sdk.settings

The settings module contains the various environment variables made available to the container by the Agent. They are as follows. 

* MODULE\_ID - UUID of the currently executing module
* AGENT\_ID - UUID of the Agent executing the Module
* C2\_URL - URL of the Master Node
* LOCAL\_IP - IP address of the Agent host machine on the local network, used for modules which perform local network tasks such as scanning.
* NETMASK - Netmask of the network corresponding to LOCAL\_IP

`   
`









 

