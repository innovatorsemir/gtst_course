# Networking for Hackers

---

## Recalling — Last Time Topics

* Introduction to Networking
* Classification of Networks
* IP Address Technology
* MAC Address
* OSI Model
* TCP and UDP Protocols
* TCP/IP Model
* Networking Devices
* Virtualization Network

---

# Introduction to Networking

* A network consists of two or more entities or objects sharing resources and information.
* A computer network consists of two or more computing devices connected to each other to share resources and information.
* The network becomes a powerful tool when computers communicate and share resources with other computers on the same network or entirely distinct networks.

### Client and Server

Computers on a network can act as a **client** or a **server**.

#### Client Computer

* A client is a computer that requests resources.

#### Server Computer

* A server is a computer that controls and provides access to resources.
* Servers generally have higher:

  * RAM
  * CPU
  * Storage

### Example

A typical server environment can contain:

```text
Server Rack → Switch → Modem → Servers → Firewall → Display
```

---

# Need of Networks

Networks are used to:

* Enhance communication.
* Share resources.
* Facilitate centralized management.
* Provide Internet access.

---

# Classification of Networks

Networks can be classified in two main ways:

1. Classification by network geography.
2. Classification by component roles.

---

# Classification by Network Geography

Networks are frequently classified according to the geographical boundaries spanned by the network itself.

The basic types are:

* LAN
* MAN
* WAN

---

## 1. Local Area Network (LAN)

* A LAN covers a relatively small area such as:

  * Classroom
  * School
  * Single building
  * Office
* LANs are inexpensive to install.
* LANs generally provide higher speeds.

---

## 2. Metropolitan Area Network (MAN)

* A MAN spans the distance of a typical metropolitan city.
* The cost of installation and operation is higher than a LAN.
* MANs can use high-speed connections such as fiber optics to achieve higher speeds.

---

## 3. Wide Area Network (WAN)

* WANs span a larger area than a single city.
* They use long-distance telecommunication networks for connection.
* This increases the cost.
* The Internet is a good example of a WAN.

---

# Classification by Component Roles

Networks can also be classified according to the roles that networked computers play in the network's operation.

Types include:

* Peer-to-peer
* Server-based
* Client-based

---

## Peer-to-Peer Network

* In a peer-to-peer network, all computers are considered equal.
* Each computer controls its own information.
* Each computer can function as either a client or a server depending on the requirement.
* Peer-to-peer networks are cheap and easy to install.
* They are popular as home networks and for use in small companies.
* Most operating systems come with built-in peer-to-peer networking capability.
* Each peer can share resources and allow others access to them.

---

## Server-Based Network

* A server-based network offers centralized control.
* It is designed for secure operations.
* A dedicated server controls the network.
* A dedicated server can:

  * Store data.
  * Store applications.
  * Store resources.
  * Provide access to resources required by clients.

---

## Client-Based Network

* Client-based networks have servers that process requests from clients and return the results.
* These networks take advantage of the processing capabilities of both the client and the server.

---

# IP Address

## Internet Protocol (IP)

* IP stands for **Internet Protocol**.
* IP is a Network Layer protocol.
* It is a way to identify machines on a network.
* An IP address is a unique identifier used to identify a device on a network.

### Uses of IP Addresses

IP addresses are used to:

* Connect to another computer or network.
* Allow transfers of files and email.
* Identify a device.

---

# IP Types

Based on IP versions:

* IPv4
* IPv6

---

# IPv4 — Internet Protocol Version 4

* An IPv4 address is a **32-bit** sequence of 1s and 0s.
* To make the IP address easier to use, it is usually written as four decimal numbers separated by periods.
* This format is called **dotted-decimal notation**.
* IP addresses can be generated automatically by DHCP or configured manually.

### IPv4 Structure

An IPv4 address consists of four sections.

Each section:

* Is **8 bits** long.
* Can range from **0 to 255**.

Example:

```text
192.168.1.10
```

Each section is called an **octet**.

```text
192    .    168    .    1    .    10
 8-bit      8-bit       8-bit    8-bit
```

### Valid IPv4 Addresses

Which of the following are valid IPv4 addresses?

1. `192.127.32.2`
2. `192.259.22.1`
3. `10.1.1.1`
4. `192,168,1,1`

Valid:

```text
192.127.32.2
10.1.1.1
```

Invalid:

```text
192.259.22.1
192,168,1,1
```

An IPv4 octet cannot be greater than `255`, and IPv4 addresses use periods (`.`) as separators.

---

# DHCP

When you connect to a network, an IP address can be generated and assigned automatically by **DHCP**.

**DHCP = Dynamic Host Configuration Protocol**

IP addresses can also be configured manually using a static configuration.

---

# Network and Host Portions

Every IP address has two logical parts:

* **Network** — identifies the network.
* **Host** — identifies the device/user on that network.

Example:

```text
Network → identifies the network
Host    → identifies a device on the network
```

The first host address is commonly used as the **gateway address** in many network configurations.

---

# IPv4 Address Classes

Traditional IPv4 classful addressing has five classes:

* Class A
* Class B
* Class C
* Class D
* Class E

> **Note:** In modern networking, CIDR and subnetting are used instead of relying on traditional classful addressing.

### Class A

* Traditionally provides a large number of host addresses.
* Has 24 host bits in its default classful structure.

### Class B

* Traditionally provides a medium number of host addresses.
* Has 16 host bits in its default classful structure.

### Class C

* Traditionally provides a smaller number of host addresses.
* Has 8 host bits in its default classful structure.
* Commonly associated with smaller networks such as home, school, and office networks.

### Class D

* Used for **multicasting**.

### Class E

* Reserved for experimental/future use.

---

# Reserved IP Addresses

Certain addresses are reserved and cannot normally be assigned to hosts.

### Loopback

Addresses beginning with `127` are reserved for loopback and internal testing.

Example:

```text
127.0.0.1
```

### Network Address

An IP address with all host bits set to `0` represents the network address.

### Broadcast Address

An IP address with all host bits set to `1` represents the broadcast address.

---

# IPv6 — Internet Protocol Version 6

* IPv6 is a **128-bit** address.
* It identifies endpoint devices in an IPv6 network.
* IPv6 addresses use hexadecimal characters.

### Example

```text
FE80:CD00:0000:0CDE:1257:0000:211E:729C
```

IPv6 addresses have:

* 128 bits.
* 8 sections.
* Sections separated by colons (`:`).
* Hexadecimal values.

### IPv4 vs IPv6

| Feature        | IPv4    | IPv6        |
| -------------- | ------- | ----------- |
| Address size   | 32 bits | 128 bits    |
| Sections       | 4       | 8           |
| Separator      | `.`     | `:`         |
| Representation | Decimal | Hexadecimal |

### Number of Possible Addresses

IPv4:

```text
2^32 = 4,294,967,296
```

Approximately:

```text
4.3 billion addresses
```

IPv6:

```text
2^128
```

Approximately:

```text
340 undecillion addresses
```

---

# Internet and Intranet

## Internet

The Internet is a worldwide network that includes different servers and networks around the world.

It provides services such as:

* Databases
* Search engines
* Social media
* Websites
* Email

## Intranet

An intranet is a local organizational network.

It can include:

* Internal servers
* Databases
* Websites
* Search systems
* Internal applications

Organizations can use VPNs to connect different regions or locations securely.

---

# Finding Your Computer's IP Address

## Windows

Use:

```bash
ipconfig
```

## Linux

You can use:

```bash
ifconfig
```

or, on modern Linux systems:

```bash
ip addr
```

---

# Private and Public IP Addresses

A host can have both a private IP address and a public IP address.

## Public IP

A public IP address is an IP address used on the WAN/Internet side of a network.

## Private IP

A private IP address is used inside a LAN/private network.

A simple analogy from the notes:

```text
Public IP → like a passport
Private IP → like an internal/local identifier
```

---

# Static and Dynamic IP Addresses

### Static IP

A static IP address is manually configured and generally remains the same until changed.

### Dynamic IP

A dynamic IP address is usually assigned automatically by DHCP.

For example:

```text
DHCP → Assigns IP → Device
```

The address may change when the device reconnects or the DHCP lease changes.

---

# Network Address Translation (NAT)

**NAT = Network Address Translation**

NAT is a method used by routers to map multiple private IP addresses inside a local network to a public IP address or a small number of public IP addresses.

### Why NAT Is Used

NAT allows devices in a private network to access the Internet without requiring every device to have its own public IPv4 address.

It also hides internal private addressing from the external network.

Example:

```text
Private Network
192.168.1.10 ─┐
192.168.1.11 ─┼──> Router/NAT ───> Public IP ───> Internet
192.168.1.12 ─┘
```

---

# Network Division

A network divided from a larger network is called a:

* Subnet
* Sub-network

Networks can be segmented and classified using different techniques.

For example, a company may receive a network allocation and divide it among different departments.

Two important techniques are:

1. VLAN
2. Subnetting

---

## VLAN

**VLAN = Virtual Local Area Network**

A VLAN allows a physical network to be logically divided into different virtual LANs.

Example:

```text
One Physical Network
        |
   +----+----+
   |         |
 VLAN 10   VLAN 20
   |         |
Sales      IT
```

---

## Subnetting

Subnetting is the process of dividing an IP network into smaller networks using subnet masks.

Example:

```text
Large Network
     |
     +---- Subnet 1
     +---- Subnet 2
     +---- Subnet 3
     +---- Subnet 4
```

---

# MAC Address

**MAC = Media Access Control**

* A MAC address is associated with a network interface.
* It is used at the Data Link layer.
* A network adapter is hardware that allows a device to connect to a network.
* Examples include:

  * Wi-Fi adapter
  * Ethernet adapter

### MAC Address Structure

A MAC address is normally **48 bits** long.

It is typically written as six hexadecimal octets.

Example:

```text
00-15-C5-49-04-A9
```

or:

```text
00:15:C5:49:04:A9
```

### MAC Address Components

A traditional MAC address can be divided into:

1. **Organizationally Unique Identifier (OUI)**
2. **Device-specific portion**

The first 24 bits are associated with the OUI.

The remaining bits are allocated by the manufacturer.

---

# OSI Reference Model

## Open Systems Interconnection Model

The **OSI model** is an internationally standardized network architecture reference model.

* It was specified in **ISO 7498**.
* It has **7 layers**.
* It provides a conceptual model for understanding how data is transferred between hosts.

### OSI Layers

From Layer 7 to Layer 1:

```text
7. Application
6. Presentation
5. Session
4. Transport
3. Network
2. Data Link
1. Physical
```

Layers 1–4 are mainly related to communication technology.

Layers 5–7 are mainly related to user applications.

---

# Network Protocols

Network protocols are rules and conventions that govern how data is transmitted and received over a network.

They define methods for communication between network devices.

### Common Network Protocols

| Protocol   | Purpose                     |
| ---------- | --------------------------- |
| HTTP/HTTPS | Web communication           |
| TCP/IP     | Core Internet communication |
| FTP        | File transfer               |
| DNS        | Domain name resolution      |
| SMTP       | Sending email               |

---

# OSI Layer 7 — Application Layer

The Application layer is where applications access network services.

It represents services that directly support software applications such as:

* File transfers
* Database access
* Email
* Web browsers

### Data Unit

```text
DATA
```

### Examples

```text
HTTP
FTP
SMTP
```

---

# OSI Layer 6 — Presentation Layer

The Presentation layer deals with the representation of transmitted data.

Responsibilities can include:

* Data translation
* Data encryption
* Data compression

### Data Unit

```text
DATA
```

### Example

```text
SSL
```

---

# OSI Layer 5 — Session Layer

The Session layer allows two applications on different computers to establish, use, and end a session.

Responsibilities include:

* Establishing sessions.
* Managing dialog control.
* Regulating which side transmits.
* Synchronization.
* Token management.

### Data Unit

```text
DATA
```

### Examples

```text
RPC
NetBIOS
```

---

# OSI Layer 4 — Transport Layer

The Transport layer manages transmission between hosts.

Responsibilities include:

* Breaking long messages into smaller segments.
* Reassembling segments.
* Error recognition and recovery.
* Acknowledging packet/segment delivery.
* Retransmitting missing data when required.

### Data Unit

```text
SEGMENTS
```

### Protocols

```text
TCP
UDP
```

---

# OSI Layer 3 — Network Layer

The Network layer manages addressing and routing.

Responsibilities include:

* Logical addressing.
* Routing.
* Determining paths between networks.
* Managing traffic.
* Controlling congestion.

### Data Unit

```text
PACKETS
```

### Examples

```text
IP
ICMP
NAT
```

---

# OSI Layer 2 — Data Link Layer

The Data Link layer packages raw bits into frames.

Responsibilities include:

* Frame creation.
* Local network communication.
* MAC addressing.
* Reliable transmission mechanisms depending on the protocol.

### Data Unit

```text
FRAMES
```

### Examples

```text
PPP
NDP
CDP
```

---

# OSI Layer 1 — Physical Layer

The Physical layer transmits bits between computers.

It defines aspects such as:

* Physical media.
* Electrical signals.
* Connectors.
* Pins.
* Transmission techniques.
* Representation of `0` and `1`.

### Data Unit

```text
BITS
```

### Example

```text
RS-449
```

### OSI Data Units Summary

```text
Layer 7 → DATA
Layer 6 → DATA
Layer 5 → DATA
Layer 4 → SEGMENTS
Layer 3 → PACKETS
Layer 2 → FRAMES
Layer 1 → BITS
```

---

# TCP and UDP

## TCP — Transmission Control Protocol

TCP is:

* Reliable.
* Connection-oriented.
* Designed to establish a connection between sender and receiver.
* Uses a three-way handshake to establish a TCP connection.

TCP is commonly used for applications where reliable delivery is important, such as:

* Web communication.
* Email.
* File transfers.
* Other applications requiring reliable data delivery.

---

## UDP — User Datagram Protocol

UDP is:

* Connectionless.
* Faster and simpler than TCP in many situations.
* Less focused on guaranteed delivery.

UDP is commonly used where low latency and speed are important, such as:

* Streaming.
* Online gaming.
* Real-time communication.

---

# TCP/IP Model

The TCP/IP model is another reference model used to understand network communication.

The commonly taught model has four layers:

```text
1. Application
2. Transport
3. Internet
4. Network Access
```

### Relationship with OSI

In the TCP/IP model:

```text
OSI Application
OSI Presentation
OSI Session
        ↓
TCP/IP Application
```

And:

```text
OSI Data Link
OSI Physical
        ↓
TCP/IP Network Access
```

---

# Networking Devices

Networking hardware devices are used to connect computers and create networks.

They can be related to OSI layers.

### Devices by OSI Layer

| OSI Layer | Devices                                   |
| --------- | ----------------------------------------- |
| Layer 7   | Firewall                                  |
| Layer 6   | No specific device in this classification |
| Layer 5   | No specific device in this classification |
| Layer 4   | No specific device in this classification |
| Layer 3   | Router, Layer 3 Switch                    |
| Layer 2   | Switch, Bridge                            |
| Layer 1   | Hub, Cables, Repeater                     |

---

# Layer 1 — Hub

A hub is a basic networking device that connects multiple devices.

It broadcasts incoming data to all connected devices.

```text
       Hub
     /  |  \
   PC1 PC2 PC3
```

---

# Layer 1 — Repeater

A repeater regenerates or boosts signals so that communication can travel farther across a network.

---

# Layer 1 — Network Cables

Network cables connect different network devices and computers.

Common types include:

1. Coaxial cable
2. Twisted-pair cable
3. Fiber-optic cable

---

## Coaxial Cable

Coaxial cables are used for:

* Cable television.
* Internet connections.
* Data transmission.

They can carry high-frequency signals with relatively low interference.

They are thicker and less flexible than some other cable types.

---

## Twisted-Pair Cable

Twisted-pair cables are widely used in:

* Telecommunication.
* Computer networks.
* Ethernet networks.

Examples include:

```text
Cat5e
Cat6
```

Over long distances, twisted-pair cables can experience signal degradation.

---

## Fiber-Optic Cable

Fiber-optic cables are used for high-speed data transmission.

Common applications include:

* Internet backbones.
* Long-distance telecommunications.
* Data centers.
* High-bandwidth environments.

Advantages:

* High bandwidth.
* Suitable for long distances.

Disadvantages:

* More expensive than many copper cable types.
* More delicate.
* Installation may require specialized skills.

---

# Layer 1 & 2 — Network Interface Card (NIC)

A **Network Interface Card (NIC)** is a hardware component that allows a computer to connect to a network.

A NIC provides:

* Physical access to a networking medium.
* Low-level network addressing through MAC addresses.

Examples:

* Ethernet NIC
* Wi-Fi NIC

---

# Layer 2 — Switch

A switch operates primarily at Layer 2.

It:

* Connects devices within the same network.
* Uses MAC addresses to forward frames.
* Can support VLANs.

Common switch sizes include:

```text
5 ports
24 ports
48 ports
```

Example:

```text
PC1 ──┐
PC2 ──┤
PC3 ──┼── Switch
PC4 ──┤
PC5 ──┘
```

---

# Layer 3 — Router

A router connects different networks.

It uses IP addresses to determine where packets should be forwarded.

Example:

```text
Network 1
192.168.1.0/24
       |
    Router
       |
192.168.2.0/24
Network 2
```

The router determines an appropriate path for traffic between networks.

---

# Modern Wi-Fi Routers

Modern home Wi-Fi routers often combine several networking devices/functions in one device.

They may contain:

1. Router
2. Switch
3. Wireless Access Point
4. Modem

---

# Layer 7 — Firewall

A firewall is a network security device or software that monitors incoming and outgoing network traffic.

It decides whether to:

* Allow traffic.
* Block traffic.

The decision is based on defined security rules.

Conceptually:

```text
Traffic
   |
   v
Firewall
  / \
Allow Block
```

## Firewall as Software

Operating systems commonly provide built-in firewall functionality.

## Firewall as a Device

Dedicated firewall appliances can be used in network infrastructure.

Example:

```text
Internet
   |
Firewall
   |
Switch
   |
Servers
```

---

# Cisco Packet Tracer

Cisco Packet Tracer is a network simulation and learning tool.

It can be used to practice:

* Network topologies.
* Routers.
* Switches.
* IP addressing.
* Network configuration.

Official resource:

https://www.netacad.com/cisco-packet-tracer

---

# Virtualization Networking

Network virtualization is the process of creating and managing virtual network resources using software.

It allows administrators to create virtual networks independently of physical networking hardware.

Examples of virtualization technologies include:

* Hypervisors
* Oracle VirtualBox
* VMware
* QEMU

Virtual machines can have different networking configurations.

Common modes include:

1. Bridged
2. NAT
3. Host-only
4. Internal Network

---

# Types of Virtual Networks

## 1. Bridged Networking

Bridged networking connects a virtual machine directly to the physical network.

The VM can receive its own IP address on the network.

```text
Physical Network
       |
   Physical NIC
       |
     Bridge
    /      \
Host       VM
          IP Address
```

---

## 2. NAT Networking

NAT networking allows virtual machines to share the host machine's network connection.

The VM typically uses a private virtual network and accesses external networks through NAT.

```text
VM
 |
NAT
 |
Host
 |
Internet
```

---

## 3. Host-Only Networking

Host-only networking allows communication between:

* The host machine.
* Virtual machines using the host-only network.

It is useful for:

* Development.
* Testing.
* Isolated lab environments.

```text
       Host
      /    \
    VM1    VM2
```

---

# Summary

At this stage, the main networking concepts covered are:

* Networking fundamentals.
* LAN, MAN, and WAN.
* Peer-to-peer networks.
* Server-based networks.
* Client-based networks.
* IPv4.
* IPv6.
* Public and private IP addresses.
* DHCP.
* NAT.
* Subnetting.
* VLANs.
* MAC addresses.
* OSI model.
* TCP and UDP.
* TCP/IP model.
* Networking devices.
* Network cables.
* Firewalls.
* Virtual networking.

These concepts provide a foundation for further cybersecurity and networking studies.

---

# Quick Revision Table

| Topic      | Key Point                                   |
| ---------- | ------------------------------------------- |
| Network    | Devices sharing resources and information   |
| LAN        | Small geographical area                     |
| MAN        | Metropolitan/city area                      |
| WAN        | Large geographical area                     |
| IP         | Logical network addressing                  |
| IPv4       | 32-bit address                              |
| IPv6       | 128-bit address                             |
| MAC        | Hardware/interface-level address            |
| DHCP       | Automatically assigns IP configuration      |
| NAT        | Maps private addresses to public addressing |
| VLAN       | Logical network segmentation                |
| Subnetting | Divides a network into smaller networks     |
| OSI        | 7-layer reference model                     |
| TCP        | Reliable, connection-oriented               |
| UDP        | Connectionless, lower overhead              |
| Hub        | Broadcasts traffic to connected devices     |
| Switch     | Forwards frames using MAC addresses         |
| Router     | Routes packets between networks             |
| Firewall   | Allows/blocks traffic based on rules        |
| NIC        | Network interface hardware                  |
| Bridged    | VM connects directly to physical network    |
| NAT        | VM shares host network connection           |
| Host-only  | VM communicates with host/isolated VMs      |

---

# OSI Model — Quick Memory

```text
7 → Application
6 → Presentation
5 → Session
4 → Transport
3 → Network
2 → Data Link
1 → Physical
```

### Data Units

```text
Application    → DATA
Presentation   → DATA
Session        → DATA
Transport      → SEGMENTS
Network        → PACKETS
Data Link      → FRAMES
Physical       → BITS
```

### Common Devices

```text
Layer 7 → Firewall
Layer 3 → Router
Layer 2 → Switch / Bridge
Layer 1 → Hub / Repeater / Cables
```

---

@innovatorsemir