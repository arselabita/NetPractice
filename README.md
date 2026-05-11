# NetPractice
*This project has been created as part of the 42 curriculum by abita.*

## Introduction
NetPractice is a systems networking project built around one simple question:
*how does data actually get from one machine to another?*

This documentation is not a surface level overview. Its a ground up reconstruction of the core concepts needed to reason about networks, starting from how two hosts communicate, all the way up to the abstractions that make the modern internet possible.

The topics covered include the layered structure of TCP/IP and OSI models, IP addressing and subnetting, and the purpose behind constructs like subnet masks, default gateways and broadcast domains. Each concept is explained not just as something to configure, but as something to *understand*, why it exists, what problem it solves, and how it fits into the bigger picture.

By the end, networking stops feeling like a black box and starts feeling like a logical, predictable system, one that can be read, debugged, and reasoned about from the ground up.

## Description
### How does machine A communicate with machine B when connected to a network?
  
  First things first, what is a network?
  - A network essentially just computers connected to each other to exchange information. These computers can be connected by using either a cable or a wireless connection. The most common way for computers to connect with each other is by using a **switch**. But whats a switch? It is a central wiring point with multiple ports so that two or more computers can connect to each other to create a network.

<p align="center">
  <img src="pictures/slazzer-preview-xtmdh.png" width="500">
</p>

- So, since we have created a network, this is called a **LAN or Local Area Network**. And a LAN is a private network. It's a type of network that you would find inside a building such as in a home, business, or an organization. So, right now the computers in this network can only talk and exchange data with each other.
  
- However, if these computers need to access another network such as the internet, they would need to contact the **Internet Service Provider** and than that ISP would send them a device called **gateway**.

<p align="center">
  <img src="pictures/slazzer-preview-enpoa.png" width="500">
</p>

- Now, a gateway is a **modem/router** combo. Then, once the gateway is connected, the computers in this local area network can now access and be a part of a **Wide Area Network or WAN**. A wide area network is a large network of millions of computers that spans over a large geographical area, such as a country, continent or even the entire globe or put in other words the **internet**.


<p align="center">
  <img src="pictures/slazzer-preview-lebzg.png" width="500">
</p>

- In our case the internet is an example of the wide area network.


## Study Resources

#### Introduction to Networking
  - [CS 198 - Introduction to the Internet](https://textbook.cs168.io/intro/intro.html)
  - [Networking Overview](https://www.youtube.com/watch?v=kNKHM_isojI)
  - [Networking (Article | A mini guide to networking)](https://datahacker.blog/industry/technology-menu/networking)

#### OSI & TCP/IP Models
  - [OSI Model (Wikipedia)](https://en.wikipedia.org/wiki/OSI_model)
  - [Brief Introduction to OSI Layers](https://docs.netgate.com/pfsense/en/latest/network/index.html#brief-introduction-to-osi-model-layers)
  - [OSI vs TCP/IP Models (Video)](https://www.youtube.com/watch?v=3b_TAYtzuho&t=75s)

#### IP Addressing Basics
  - [What is an IP Address? (Video)](https://www.youtube.com/watch?v=5WfiTHiU4x8&list=PLIhvC56v63IKrRHh3gvZZBAGvsvOhwrRF)
  - [What is an IP Address? (Article)](https://www.fortinet.com/resources/cyberglossary/what-is-ip-address)
  - [Public vs Private IP Address](https://docs.netgate.com/pfsense/en/latest/network/addresses.html)
  - [Static vs Dynamic IP Address](https://www.fortinet.com/resources/cyberglossary/static-vs-dynamic-ip)
  - [DHCP (Dynamic Host Configuration Protocol)](https://www.fortinet.com/resources/cyberglossary/dynamic-host-configuration-protocol-dhcp)

#### Routes and Rules
  - [Routers, Routes, Subnets, and Netmask](https://datahacker.blog/industry/technology-menu/networking/routers,-routes,-subnets,-and-netmasks)
  - [What is a gateway? (Article)](https://datahacker.blog/industry/technology-menu/networking/routes-and-rules/gateways)
  - [Introduction to Split Gateways](https://datahacker.blog/industry/technology-menu/networking/routes-and-rules/introduction-to-split-gateways)

#### Subnetting and CIDR
  - [IP Addres, Subnet & Gateway Configuration](https://docs.netgate.com/pfsense/en/latest/network/subnets.html#ip-address-subnet-and-gateway-configuration)
  - [IP Subnet Concepts](https://docs.netgate.com/pfsense/en/latest/network/subnets.html)
  - [Understanding CIDR](https://docs.netgate.com/pfsense/en/latest/network/cidr.html)
  - [CIDR (Cheat Sheet)](https://subnet.im/cheat-sheet)
  - [Subnet (Cheat Sheet)](https://subnet.im/cheat-sheet)

#### Core Networking Protocols
  - [TCP/IP Overview](https://www.fortinet.com/resources/cyberglossary/tcp-ip)
  - [DNS (Domain Name System)](https://www.fortinet.com/resources/cyberglossary/what-is-dns)

#### Network Concepts
  - [Broadcast Domains](https://docs.netgate.com/pfsense/en/latest/network/broadcast-domains.html)
