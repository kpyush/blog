# Wireless Communication Architecture for IOT.

Connecting the things wirelessly provides the following benifits:
* Provides scalability.
* Minimizes installation and mainenace effort.
* Mobility

To begin with proper selection of the communication architecture & underlying protocol palys major role to achieve the above mentioned requirements. This document explains various technologies of communication, architecture & available SoCs in the market. Before going into much detail let's figure out some basic requirement of Iot devices in genral.

**Selection of Wireless Mesh Network Vs Star Network:**

When we start thinking about the network topology following the following questions comes in mind.

Q1: Why newer technologies are adopting mesh topology instead of star (Zigbee, Zwave, Thread, BLE mesh). Which is significant contrast between usual star topology of wifi where every device connects to router which act as concentrator. 

Q2: [EETimes](https://www.eetimes.com/document.asp?doc_id=1168414) suggest that reliability improvements (e.g. self-healing transmissions) are one of the main advantages of a mesh network, though this seems like a small advantage compared to the added complexity of setting up a mesh network.

Q3: For a home/office IoT network which is likely to contain about 10-20 networked devices and spread a short range from end-to-end, what makes mesh networks more suitable than a regular star topology? Is the added complexity not as significant as I seem to believe it is?

For answering these questions let's go back in time when only wired technologies were available.
