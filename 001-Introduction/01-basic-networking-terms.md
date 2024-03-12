# Basic Networking Terms

## What is a Network?

**Q) Why do we have computer networks?**
**A)** We want to share information or share some kind of resource with someone else. Let us say you have 100 employees and each of them need to use a printer, you can just have 10 printers that is shared by 100 people. You have a resource that is shared with multiple clients. Idea is rather than having to physically transfer data, we digitally do it.

- A Computer Network is a digital telecommunications network for sharing resources between nodes, which are computing devices that use a common telecommunications technology.
- Data transmission between nodes is supported over data links consisting of physical cable media, such as twisted-pair or fibre optic cables, or by wireless methods, such as wifi or microwave.

Networks can range from massive, global structures like the Internet, the largest known network on Earth, to very simple connections between just two computers. The essential purpose of a network is to facilitate the sharing of resources and information. Networks do not have to be large; a minimal network can consist of just two computers.

## Basic Networking Concepts

- **Without a Network:** Initially, to share files between two computers without a network, one would use a USB drive to copy and transfer files manually.

- **Ethernet Cabling:** In its basic form, networking can utilize physical cables, specifically Unshielded Twisted Pair (UTP) copper cables with RJ45 connectors. This setup is an example of a wired Ethernet network.

- **Network Interface Card (NIC):** NICs are crucial for connecting to a network, either physically through a cable or wirelessly. NICs have a unique MAC (Media Access Control) address. Older laptops might have built-in RJ45 ports for Ethernet cables, while newer models may require adapters due to the absence of these ports.

## Evolution of Ethernet and Networking Technologies

- **From Thicknet to Thinnet:** Ethernet technology has evolved from the original 10base5 (thicknet) to 10base2 (thinnet) and now commonly uses Cat5e or Cat6 UTP cabling. Thicknet was cumbersome and used a bus network topology, making it difficult to manage and connect devices.

- **Wireless Connectivity:** Modern networking often relies on wireless technologies like Wi-Fi and Bluetooth for data transmission, eliminating the need for physical cables and simplifying the process of sharing files between devices, such as smartphones.

- **USB to RJ45 Adapters:** For devices lacking an RJ45 port, USB to RJ45 adapters can bridge the gap, allowing them to connect to wired Ethernet networks.

- **Category of Cabling:** Ethernet cables have evolved over time, with categories such as Cat5e and Cat6 offering improvements in speed and performance. These cables are commonly used in both home and office networks.

- **Fiber Optics:** Besides copper UTP cabling, fiber optic cables are another medium for network connectivity, offering higher speeds and longer range. Fiber optics come in multi-mode and single-mode varieties, catering to different networking needs.

## Networking in Practice

- **Sharing Files Between Devices:** The essence of networking is to share resources, such as files, between devices. This can be achieved through various means, including wired connections using Ethernet or wireless technologies like Wi-Fi and Bluetooth.

- **Importance of NICs:** Whether a device connects to a network using wires or wirelessly, it requires a NIC, which could be built-in or external, to access the network. The NIC's MAC address serves as a unique identifier within the network.

> Airdrop in apple products creates its own wifi network that allows two devices to share files without the need for any wifi networks.

#### Modulation

- **Modulation** is the process of varying one or more properties of a periodic waveform, called the carrier signal, with a modulating signal that typically contains information to be transmitted.
- Most radio systems in the 20th century use frequency modulation (FM) or amplitude modulation (AM) for radio brodcast.

## Server-Client Model Overview

- **Server Definition:** A server is a computer program or device that provides functionality for other programs or devices, known as clients. This architecture is called the client-server model, where a single overall computation is distributed across multiple processes or devices.

- **Client Definition:** A client is a piece of computer hardware or software that accesses a service made available by a server. The service is often hosted on a different computer system, and the client accesses it via a network.

## Key Concepts in Networking

- **Resource Sharing:** The primary function of a network is to enable the sharing of resources and information between computing devices (nodes).

- **Server's Role:** Servers offer various services or functionalities to clients. These can include web hosting, file storage, and application services. Servers are designed to handle multiple requests and can be scaled to manage thousands of queries from many clients simultaneously.

- **Client's Role:** Clients access services provided by servers. This can be as simple as requesting a web page from a web server or accessing a shared file on a file server.

## Hardware and Protocols

- **Server Hardware:** Servers are typically robust machines with considerable storage, computing power, and memory to manage large volumes of requests. They can host multiple drive bays and are designed to scale as demand increases.

- **Protocols:** Communication between devices on a network is governed by protocols, which are sets of rules for data exchange. Protocols ensure that devices can understand and respond to each other's requests correctly.

- **Ports and Protocols:** Servers listen on specific port numbers for various protocols to provide different services. For example, web servers typically listen on ports 80 (HTTP) and 443 (HTTPS), while FTP servers listen on port 21.

## Practical Examples

- **Distributed Services:** Large-scale services, like those provided by Google, utilize thousands of servers to manage requests from millions of clients. These services are distributed across multiple servers to ensure availability and reliability.

- **Multi-functionality of Devices:** A single device can act as both a client and a server depending on the context. For example, a laptop could request a web page from a web server (acting as a client) or host a file-sharing service (acting as a server).

- **Networking and Automation:** In modern networking, the concept of network programmability and automation is increasingly important, with applications and programs communicating with each other via APIs (Application Programming Interfaces) to automate tasks and services.

# Building a Basic Network in Packet Tracer

This guide will walk you through setting up a basic network in Packet Tracer, involving a server and a client PC. You'll learn how to establish connectivity, assign IP addresses, and demonstrate the client-server model.

## Step 1: Launch Packet Tracer

- Open Cisco Packet Tracer on your computer.

## Step 2: Add Devices to Your Workspace

1. Navigate to the **End Devices** section.
2. Select a **Server** and drag it into your workspace.
3. Choose a **PC** (representing a traditional computer or laptop) and add it next to the server.

## Step 3: Connect the Devices

1. Select **Connections** from the bottom of the screen.
2. Choose the **Copper Cross-Over** cable. In modern networks, Auto-MDIX typically allows for using straight-through cables for PC to PC or PC to Server connections, but Packet Tracer simulates older networking behaviors requiring a crossover cable for such connections.
3. Connect one end of the cable to the FastEthernet port on the PC and the other end to the FastEthernet port on the Server.

## Step 4: Configure IP Addresses

Since we don't have a DHCP server in this basic setup, you need to assign static IP addresses to both the server and the client PC.

### For the PC:

1. Click on the PC > **Desktop** tab > **IP Configuration**.
2. Enter an IP address (e.g., `10.1.1.1`) and a subnet mask (typically `255.255.255.0`).

### For the Server:

1. Click on the Server > **Desktop** tab > **IP Configuration**.
2. Assign it a different IP address in the same subnet (e.g., `10.1.1.2`) and the same subnet mask (`255.255.255.0`).

## Step 5: Test Connectivity

1. On the PC, open the **Command Prompt**.
2. Type `ping 10.1.1.2` (replace `10.1.1.2` with the server's IP address).
3. You should see replies from the server, indicating successful communication.

## Step 6: Explore Client-Server Interactions

### Enable HTTP Service on the Server:

1. Click on the server.
2. Go to the **Services** tab.
3. Select **HTTP** and ensure it is turned on. You can also enable **HTTPS** for secure communications.

### Access the Server from the PC:

1. On the PC, open a **Web Browser**.
2. Enter the server's IP address (`http://10.1.1.2`) in the URL field.
3. You should be able to view the default web page served by the server, demonstrating the client-server interaction.

## Understanding the Client-Server Model

- The PC acts as a client requesting services (web page) from the server.
- By changing roles or services, any device can act as a server or a client depending on the context.

# Understanding Network Devices: Past and Present

This overview will guide you through the evolution of networking devices from the earliest repeaters to modern intelligent switches and routers, illustrating how each device contributes to the fabric of network communication.

## Early Networking Devices

### Repeaters and Hubs

- **Repeater:** An early networking device used to amplify the signal from one port to another, combating signal attenuation over long distances. It worked with early Ethernet standards like 10base5 and 10base2 but lacked intelligence, merely amplifying signals without understanding their content.

- **Hubs (Multiport Repeaters):** Hubs are essentially multiport repeaters. Connecting devices via RJ45 connectors, hubs amplify and repeat incoming signals to all other ports indiscriminately. This lack of intelligence means all devices connected to a hub share bandwidth, leading to potential collisions and reduced network efficiency.

## Transition to Intelligence

### Bridges and Switches

- **Bridges:** Serving as an intermediary between hubs and switches, bridges began the introduction of intelligence into network devices. They learned the MAC addresses of devices and could forward frames to the correct destination, reducing unnecessary traffic and collisions compared to hubs.

- **Switches:** Modern switches are highly intelligent devices that maintain a MAC address table to forward frames only to the intended recipient port. This significantly reduces network traffic and collisions. Switches operate at Layer 2 of the OSI model, using Ethernet frames for communication. Unlike hubs, which are Layer 1 devices and simply repeat signals, switches understand and manage network traffic efficiently.

> A **bridge** learns MAC addresses in software but a **switch** learns MAC addresses much more quickly by using hardware ASICs (Application specific integrated circuits). These devices typically work on a local area network (LAN).

## Modern Networking Devices

### Routers

- **Routers:** Routers are sophisticated devices that route traffic between different networks, operating at Layer 3 of the OSI model. They use IP addresses to send data from one network to another, typically from a local area network (LAN) to a wide area network (WAN). Modern routers often combine routing, switching, and wireless access point functionalities to cater to diverse networking needs.

### Wireless Access Points

- **Wireless Access Points (WAPs):** WAPs enable devices to connect to a wired network using Wi-Fi. While they bring the convenience of wireless communication, the medium (air) is shared among devices, much like the early hubs. Modern WAPs, especially those supporting Wi-Fi 6, incorporate technologies to manage airtime more efficiently, but the basic principle of sharing the medium remains.

### Router Example

- **Example:** Cisco 4321 Router
- **Functionality:** Routers are crucial for connecting different networks together, such as connecting a local area network (LAN) to the internet (a wide area network, WAN). They use IP addresses to direct data to its destination across networks.

### Switch Example

- **Example:** Cisco 3560-CX Switch and 2960 Switch
- **Characteristics:** Switches are used within LANs to connect various devices like computers, printers, and servers. They are intelligent devices that can learn the MAC addresses of connected devices to efficiently forward data only to its intended recipient.

### Firewalls

- **Example:** Cisco ASA 5505
- **Purpose:** Firewalls serve as security devices that monitor and control incoming and outgoing network traffic based on predetermined security rules. They can be standalone devices or integrated into routers and are essential for protecting network security.

### Wireless LAN Controllers

- **Usage:** A wireless LAN controller (WLC) manages wireless access points in a network, particularly useful in large deployments. Instead of configuring each access point individually, a WLC allows for centralized management, making it easier to control and adjust settings for multiple access points simultaneously.

## Advanced Security Devices

### Intrusion Detection and Prevention Systems (IDS/IPS)

- **IDS:** Acts like a watchdog, alerting you to potential threats or attacks on your network without taking direct action against them.
- **IPS:** Sits in-line with network traffic and can both detect threats and take action to block them, preventing unauthorized access or attacks on the network.

## Analogies to Understand IDS/IPS

- **IDS is like a small dog:** It can alert you to danger by barking (detecting an intrusion) but doesn't have the capability to stop the intruder.
- **IPS is like a large guard dog:** Not only can it alert you to the presence of an intruder by barking, but it can also take direct action to prevent the intruder from entering (stopping attacks).
