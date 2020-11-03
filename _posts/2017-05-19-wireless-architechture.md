---
layout: post
title: "Wireless Communication Architecture for IOT"
categories: Wireless
---

Connecting the things wirelessly provides the following benifits:
* Provides scalability.
* Minimizes installation and mainenace effort.
* Mobility

Selection of the communication architecture & underlying protocol palys major role to achieve the above mentioned requirements. This document explains various technologies of communication, architecture & available SoCs in the market. Before going into much detail let's figure out some basic requirement of IoT devices in genral.

**Selection of Wireless Mesh Network Vs Star Network:**

When we think about the network topology following the following questions pops up in our mind.

* Why newer technologies like Zigbee, Zwave, Thread and BLE-MESH are adopting mesh topology instead of star, which is significant contrast between usual star topology of WiFi where every device connects to router which act as concentrator. 

* [EETimes Blog](https://www.eetimes.com/document.asp?doc_id=1168414) states that reliability improvements (e.g. self-healing transmissions) are one of the main advantages of a mesh network, though this seems like a small advantage compared to the added complexity of setting up a mesh network.

* For a home/office IoT network which is likely to contain about 10-20 networked devices and spread a short range from end-to-end, what makes mesh networks more suitable than a regular star topology? Is the added complexity not as significant as I seem to believe it is?

For answering these questions let's go back in time when only wired technologies were available.

## Wired mesh network vs. star topology:

Well, the Internet is a mesh network. Why? Because DARPA wanted it to work even if half the United States were bombed into oblivion if the cold war was going hot. The military wanted a highly reliable network that is not dependent on any single node. Meshing or at least partial meshing your network nodes will give you that reliability. The major drawback of (wired) mesh networks is that they are not very cost efficient. They cost a lot. Cabling every component to every other component is just too expensive. So the WAN backbone of the Internet of Things is already a wired mesh network.

Star topology is needs just one cable per node, while meshing uses up to n*(n-1)/2 for a full mesh. The cabling for mesh networks gets a lot more expensive very fast. Thus, star topology emerged as the dominant standard.


## Wireless mesh networks:

Establishing wireless mesh networks overcomes the major drawback of wired mesh networks. There is no cabling cost to create a wireless mesh network. Thus, creating wireless mesh networks pairs the reliability network creators always wanted with the low cost of few cables and of course all the other advantages of being wireless.However there are still a few drawbacks of mesh networks. Nodes have to be relatively smart for the routing compared to simply connecting to one central node. ZigBee uses Ad hoc On-Demand Distance Vector Routing, which requires routing tables at each node. Also a certain duplex capability of the nodes is required to make the network efficient. Bringing that on a low-cost, wireless-capable microchip took some time. Today we have those chips.For a mesh network to work properly there have to be enough nodes. It actually gets more efficient with more nodes (that connect to at least two existing ones). Thus, the Internet of Things were everything can act as a node is an obvious match for meshed networks. While other topologies would possibly clog up with more nodes mesh networks really start to shine there and get faster and more reliable the more nodes are added.


## 10 -20 node network: 
For a smart home setting with one or two dozen devices there are a few things to consider regarding topology. Firstly, ZigBee actually supports star topology as well. Secondly, any sort of distance vector routing usually works with weighted vector values. Thus, in a smart home setting the direct connection could very well be rated highest and you'll end up with a star topology even when it's configured as a mesh.
Only the device that are out of range of a central component like a Hue Bridge (or rate the direct connection bad enough) will even make use of the mesh topology. For these devices mesh networking is essentially a low latency range extension for your network. Thus, you don't have to buy another central node. That saves money. So the same thing that killed wide spread wired mesh networks before makes wireless mesh networks so attractive today.
