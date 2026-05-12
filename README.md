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

### IP addresses, subnet masks, gateways, switches, routers.

- Now a lot of times what may happen in a lot of businesses is that they may have different departments. 
- For example: they may have a *service department* and a *sales department*. And a lot of times that business may want to **separate** **the computer network data** in the different departments from each other so that the sales department doesn't see **any network traffic** from the service department and vice versa. So, what a business will do is that they wil **divide their own LAN** into two **smaller networks**.

<p align="center">
  <img src="pictures/slazzer-preview-elr82.png" width="500">
</p>

- These smaller networks are called **subnetworks**. And shorter way to refer to is **subnet**. A subnet is just a division of a bigger network. So, this network here is still a LAN but within that LAN we have two subnetworks or subnets.

-  Now, what divides a network from another network is a **router**. A router is the doorway or the gateway to a network. So, this router here is what's separating these two subnets.

<p align="center">
  <img src="pictures/slazzer-preview-5wfhg.png" width="500">
</p>

- Also, this network is **not** just **limited** to **creating** just two **subnets**, it can create how many it wants, it just depends on the needs of the business. So, if this business expanded and they wanted to create another department, they can further separate this network and create a third subnet by adding another router. So, now the LAN has three subnets.

<p align="center">
  <img src="pictures/slazzer-preview-i46ef.png" width="500">
</p>

- Moreover, the **reason why** an organization or business would create subnets is to **separate** the **network traffic**. This could be for several different reasons, such as:
    1. **Manageability**: Because, if any problems happen on a network it would be easier to pinpoint on smaller networks than on large networks.
    2. **Security**: Subnets can have their own separate security rules to either allow or deny access to certain data.
    3. **Improve the performance**: This by controlling broadcast traffic. When a computer wants to communicate with other computers on a network it sends out the broadcast to every computer on the network. So, every computer can hear the broadcast traffic from every other computer. But, by braking down a network into smaller subnets, the broadcast are heard by other computers on the same subnet, therefore limiting the amount of broadcast traffic.

As a review the internet with all of its computers, servers, and routers is an example of a WAN. But, within that Wide Area Network there are LANs. These are private networks that are in organizations, businesses and homes. And within those LANs we have subnets which are divisions of larger networks.

<p align="center">
  <img src="pictures/aa.png" width="500">
</p>

Now, we talked about all these components but we still don't know what's an **IP address**?

An IP address is an **identifier** for a computer or device on a network. Every device has to have an IP address for communication purposes. And, to be more specific, **IPv4 address**. An IPv4 address is a *32-bit numeric address*, written as four numbers, separated by periods. 

<p align="center">
  <img src="pictures/bb.png" width="500">
</p>

Each group of numbers that are separated by periods are called an octet. And the number range in each octet is from 0 - 255.

<p align="center">
  <img src="pictures/ss.png" width="500">
</p>

The IP address consists of **two parts**.
  1. The first part is the **network address**. It is a number that is assigned to a network. So, that every network as a unique address.
  2. The second part is the **host address**. It is assigned to hosts within that network such as computers, servers, tablets, routers, and so on. So, every host will have a unique host address.

Now, how do we tell which is the network address and the host address in an IP address?

Here, is where the **subnet mask** number comes into play. As we know by now, a subnet mask or subnet is *a number that resembles an IP address*. And it reveals how many bits in the IP address are used for the network by masking the network portion of the IP address.

Why does an IP address have a network part and a host part?

The reason for this is for breaking down a large network into a smaller network or subnetworks, which is known as **subnetting**.

Imagine this, consider we have an organization and it has a large amount of computers connected to a huge network. Now, when a computer wants to exchange messages with another computer, it needs to know how and where to reach that computer. It does this by using a **broadcast**.

<p align="center">
  <img src="pictures/broadcasts1.png" width="500">
</p>

A broadcast is essentially when a computer sends out data to all computers on the network so it can locate and talk to a certain computer. But, in the end, even if we locate the computer in this case, the idea behind this is that in any case these computers in this corporate will be constantly sharing data and communicating with each other. And, if every computer is broadcasting to find the address for its message destination it would be a chaos, a lot of traffic of data and would be too hard to pinpoint the issues and troubleshoot.

And, this is why in order to prevent this, large networks should need to be broken down into smaller networks, and networks are broken down and physically separated by using **routers**. By using routers this would solve the problem of traffic because broadcasts do not go beyond routers. Broadcasts stay within the network.

<p align="center">
  <img src="pictures/subnetworks.png" width="500">
</p>

So, instead of a large network, this network is broken down into 6 subnetworks or subnets. If one computer wants to communicate with another one, the computer with send out a broadcast that only the computers within that subnetwork will. But, since that computer it wants to communicate with is in another subnetwork, the data will be sent to the **default gateway**, *which is the router*, and then the router will intelligently route the data to the destination.

This is why IP addresses have a network portion and a host portion, so networks can be logically broken down into smaller networks which is known as subnetting. 


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
