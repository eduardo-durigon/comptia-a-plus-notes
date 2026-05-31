# Module 5 – Networking Hardware and Wireless Technologies

## CompTIA A+ Core 1 (220-1201)

---

# Overview

This module focused on networking hardware, network types, cabling standards, wireless technologies, and the infrastructure used to connect devices across modern networks. The lessons covered how local and wide-area networks operate, how data is transmitted through copper and fiber cabling, and how wireless communication technologies provide network connectivity.

The module also explored:

* LAN, WAN, WLAN, MAN, PAN, and SAN networks
* SOHO and Enterprise network design
* Data centers and network infrastructure
* Network Interface Cards (NICs)
* MAC addressing
* Patch panels and structured cabling
* Ethernet switching
* Managed and unmanaged switches
* Power over Ethernet (PoE)
* Copper and fiber-optic cabling
* Ethernet cable standards and categories
* Wireless networking standards
* Access points and wireless configuration
* Wi-Fi frequency bands
* Bluetooth, RFID, and NFC technologies

This module emphasized understanding how network infrastructure operates and how technicians deploy, manage, and troubleshoot modern wired and wireless networks.

---

# 5.1 Network Types

## Local Area Networks (LAN)

A Local Area Network (LAN) consists of devices connected within a limited geographic area such as:

* a room
* an office
* a building
* a campus

Most LANs use Ethernet standards maintained by the IEEE.

### Common Ethernet Standards

| Standard   | Speed    |
| ---------- | -------- |
| 100BASE-T  | 100 Mbps |
| 1000BASE-T | 1 Gbps   |
| 10GBASE-T  | 10 Gbps  |

LANs commonly use:

* copper twisted-pair cabling
* Ethernet switches
* fiber backbones

---

## Wide Area Networks (WAN)

A Wide Area Network (WAN) connects multiple geographic locations.

Examples include:

* the Internet
* corporate branch offices
* multi-site organizations

WAN connectivity is typically provided through an Internet Service Provider (ISP).

---

## Wireless LANs (WLAN)

Wireless LANs use radio frequencies instead of physical cabling.

### Characteristics

* Based on IEEE 802.11 standards
* Commonly known as Wi-Fi
* Supports mobility
* Simplifies deployment
* Can integrate with wired LANs

---

## Metropolitan Area Networks (MAN)

A MAN connects networks across a city or municipality.

Characteristics:

* Larger than a LAN
* Smaller than a WAN
* Often used by municipalities and large organizations

---

## Personal Area Networks (PAN)

PANs connect personal devices within a short range.

Examples:

* smartphones
* smartwatches
* wireless earbuds
* Bluetooth accessories

---

## Storage Area Networks (SAN)

A SAN is a dedicated network used exclusively for storage traffic.

### SAN Features

* Dedicated storage network
* Block-level access
* High-speed connectivity
* Centralized storage management

Commonly used in:

* data centers
* enterprise environments
* virtualization platforms

---

# 5.1.2 SOHO and Enterprise Networks

## SOHO Networks

Small Office/Home Office (SOHO) networks are designed for:

* homes
* small businesses
* remote offices

Characteristics:

* simple design
* limited users
* lower cost
* fewer networking devices

---

## Enterprise Networks

Enterprise networks support:

* large user populations
* multiple locations
* centralized management
* increased redundancy
* enhanced security

Common components include:

* switches
* routers
* firewalls
* wireless controllers
* servers

---

## Data Centers

A data center is a facility dedicated to housing:

* servers
* storage systems
* networking equipment

Data centers provide:

* high availability
* redundancy
* environmental controls
* centralized infrastructure

---

# 5.2 Networking Hardware

## Network Interface Cards (NICs)

A NIC provides the physical network connection for a device.

Functions include:

* transmitting data
* receiving data
* storing MAC addresses
* connecting to Ethernet networks

Modern NICs commonly support:

* 1 Gbps
* 2.5 Gbps
* 10 Gbps

---

## MAC Addresses

Every NIC contains a unique MAC address.

### MAC Address Characteristics

* 48-bit identifier
* Written in hexadecimal
* Six groups of two characters

Example:

00:60:8C:12:3A:BC

### Components

* First 24 bits = Organizationally Unique Identifier (OUI)
* Last 24 bits = Device-specific identifier

---

## Patch Panels

Patch panels organize network cabling inside structured cabling systems.

Benefits:

* easier cable management
* simplified troubleshooting
* improved scalability
* organized infrastructure

---

## Switches

Ethernet switches connect devices within a network.

### Switch Functions

* Learn MAC addresses
* Forward frames intelligently
* Reduce collisions
* Improve network efficiency

Unlike hubs, switches send traffic only to the destination port when possible.

---

## Managed vs Unmanaged Switches

### Unmanaged Switches

* Plug-and-play
* No configuration required
* Common in small networks

### Managed Switches

* Configurable
* Support VLANs
* Monitoring capabilities
* Advanced security options
* Enterprise deployment

---

# 5.2.10 Power over Ethernet (PoE)

Power over Ethernet allows network cables to provide:

* data connectivity
* electrical power

Common PoE devices include:

* wireless access points
* IP cameras
* VoIP phones
* security devices

---

## PoE Standards

| Standard        | Power     |
| --------------- | --------- |
| 802.3af (PoE)   | 15.4W     |
| 802.3at (PoE+)  | 25W       |
| 802.3bt (PoE++) | Up to 90W |

---

# 5.3 Network Cabling

## Unshielded Twisted Pair (UTP)

UTP is the most common Ethernet cabling type.

Advantages:

* inexpensive
* flexible
* easy to install

---

## Shielded Twisted Pair (STP)

STP provides additional protection against:

* electromagnetic interference (EMI)
* crosstalk

Commonly used in electrically noisy environments.

---

## Ethernet Cable Categories

| Category | Maximum Speed                   |
| -------- | ------------------------------- |
| Cat5     | 100 Mbps                        |
| Cat5e    | 1 Gbps                          |
| Cat6     | 1 Gbps (10 Gbps short distance) |
| Cat6A    | 10 Gbps                         |
| Cat7     | 10 Gbps                         |
| Cat8     | 25–40 Gbps                      |

---

## RJ45 Connectors

RJ45 connectors terminate Ethernet cabling.

### Termination Standards

* T568A
* T568B

Both standards function properly as long as both cable ends use the same wiring scheme.

---

## Cable Testing Tools

### Cable Tester

Used to verify:

* continuity
* proper pinout
* successful termination

### Tone Probe

Used to identify cables within bundles and patch panels.

### Loopback Plug

Used to test:

* NICs
* switch ports
* network interfaces

---

## Plenum Cable

Plenum cable is designed for installation within HVAC air spaces.

Characteristics:

* fire-resistant jacket
* low smoke production
* building code compliance

---

## Direct Burial Cable

Designed for outdoor installations.

Features:

* moisture resistance
* UV resistance
* environmental protection

---

# 5.3.11 Fiber Optic Cabling

Fiber optic cable transmits data using pulses of light.

Advantages:

* extremely high bandwidth
* long-distance communication
* immunity to EMI

---

## Single-Mode Fiber (SMF)

Characteristics:

* Small core
* Long-distance communication
* Laser light source
* Higher bandwidth

---

## Multi-Mode Fiber (MMF)

Characteristics:

* Larger core
* Shorter distances
* Lower cost
* Common in LAN environments

---

## Fiber Connectors

### ST Connector

* Twist-lock design

### SC Connector

* Push-pull design

### LC Connector

* Small form-factor connector
* Common in modern networking

---

## Coaxial Cabling

Coaxial cable contains:

* center conductor
* insulation
* shielding
* outer jacket

Common uses:

* cable television
* broadband Internet
* CCTV systems

---

# 5.4 Wireless Networking Technologies

## Wireless Networking Fundamentals

Wireless networks use radio frequencies to transmit data.

Most WLANs are based on:

* IEEE 802.11 standards

Wireless infrastructure typically includes:

* access points
* client devices
* wireless controllers

---

## Access Points (APs)

An access point provides wireless connectivity to network clients.

Functions include:

* transmitting wireless signals
* receiving client traffic
* bridging wireless and wired networks

---

## Wireless Frequency Bands

### 2.4 GHz

Advantages:

* longer range
* better obstacle penetration

Disadvantages:

* more interference
* lower throughput

---

### 5 GHz

Advantages:

* faster speeds
* more channels
* reduced interference

Disadvantages:

* shorter range

---

### 6 GHz

Advantages:

* highest throughput
* least congestion
* additional channels

Disadvantages:

* shortest range

---

## Wireless Standards

### 802.11b

* 2.4 GHz
* 11 Mbps

### 802.11g

* 2.4 GHz
* 54 Mbps

### 802.11n (Wi-Fi 4)

* 2.4 GHz and 5 GHz
* MIMO support

### 802.11ac (Wi-Fi 5)

* 5 GHz
* Channel bonding
* MU-MIMO

### 802.11ax (Wi-Fi 6)

* 2.4 GHz and 5 GHz
* Improved efficiency
* OFDMA
* Enhanced MU-MIMO

---

## Channel Bonding

Channel bonding combines multiple channels to increase throughput.

Common channel widths:

* 20 MHz
* 40 MHz
* 80 MHz
* 160 MHz

---

## MIMO and MU-MIMO

### MIMO

Multiple antennas improve:

* reliability
* throughput
* signal quality

### MU-MIMO

Allows an access point to communicate with multiple clients simultaneously.

---

## Wireless Configuration Considerations

When configuring wireless networks:

* Select appropriate channels
* Avoid channel overlap
* Choose proper frequency bands
* Configure SSIDs appropriately
* Implement strong security settings

---

## Wi-Fi Analyzers

Wi-Fi analyzers help technicians:

* measure signal strength
* identify interference
* locate channel congestion
* optimize wireless performance

Signal strength is commonly measured in:

* dBm

---

# Bluetooth, RFID, and NFC

## Bluetooth

Bluetooth is a Personal Area Network (PAN) technology.

Common uses:

* headphones
* speakers
* keyboards
* mice
* smartphones

### Bluetooth Low Energy (BLE)

BLE is optimized for:

* low power consumption
* IoT devices
* wearable technology

---

## RFID

Radio Frequency Identification (RFID) uses radio waves to identify and track objects.

Applications include:

* inventory management
* asset tracking
* access control

---

## NFC

Near Field Communication (NFC) is a short-range RFID technology.

Common uses:

* contactless payments
* identification systems
* mobile device pairing

---

# Important Exam Notes

## Key Terms

| Term    | Meaning                                   |
| ------- | ----------------------------------------- |
| LAN     | Local Area Network                        |
| WAN     | Wide Area Network                         |
| WLAN    | Wireless Local Area Network               |
| PAN     | Personal Area Network                     |
| SAN     | Storage Area Network                      |
| NIC     | Network Interface Card                    |
| MAC     | Media Access Control Address              |
| PoE     | Power over Ethernet                       |
| UTP     | Unshielded Twisted Pair                   |
| STP     | Shielded Twisted Pair                     |
| RFID    | Radio Frequency Identification            |
| NFC     | Near Field Communication                  |
| MIMO    | Multiple Input Multiple Output            |
| MU-MIMO | Multi-User Multiple Input Multiple Output |

---

# Key Takeaways

* LANs connect devices within a limited geographic area, while WANs connect multiple locations.
* NICs and MAC addresses are fundamental components of network communication.
* Switches improve network efficiency by forwarding traffic intelligently.
* PoE simplifies device deployment by delivering power and data through a single cable.
* Cat6A and newer cable standards support high-speed Ethernet networks.
* Fiber optic cabling provides greater bandwidth and longer transmission distances than copper cabling.
* Access points bridge wireless devices to wired networks.
* The 5 GHz and 6 GHz bands provide higher performance than 2.4 GHz but at shorter ranges.
* Wi-Fi 6 improves efficiency and performance in high-density wireless environments.
* Bluetooth, RFID, and NFC provide specialized short-range wireless communication technologies.

---

# Reflection

This module significantly expanded my understanding of modern network infrastructure and the technologies that allow devices to communicate across wired and wireless networks. I learned how different network types are designed for specific purposes, how Ethernet networks operate, and how switches, NICs, patch panels, and structured cabling work together to create reliable network environments.

The cabling sections gave me a much better understanding of Ethernet standards, cable categories, fiber optics, and proper installation practices. I also gained valuable knowledge about wireless networking, including access points, Wi-Fi standards, frequency bands, channel selection, MIMO technologies, and wireless optimization.

Overall, this module reinforced the importance of understanding both physical and wireless networking infrastructure. It provided a strong foundation for future studies in network administration, troubleshooting, cybersecurity, and enterprise IT environments.
