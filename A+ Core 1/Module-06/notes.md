# Module 6 – Network Communications

## What I Studied

This module focused on how devices communicate across local and wide area networks using TCP/IP networking standards. I learned how hosts are identified on networks, how data is routed between devices, and how common internet services use network protocols to exchange information.

The module covered:

* IPv4 and IPv6 addressing
* Network prefixes and subnet masks
* Public and private IP addresses
* Default gateways and routing
* Static and dynamic IP addressing
* DHCP operation and address leasing
* DNS hierarchy and resource records
* TCP and UDP communication
* Common network protocols and ports
* VLANs and VPNs

---

## Key Concepts

### IPv4 Addressing

An IPv4 address is a 32-bit value divided into a network portion and a host portion. Subnet masks and prefix notation are used to determine which part identifies the network and which part identifies individual hosts.

Examples:

* 192.168.0.0/24
* 255.255.255.0

Private IPv4 address ranges:

* 10.0.0.0 – 10.255.255.255
* 172.16.0.0 – 172.31.255.255
* 192.168.0.0 – 192.168.255.255

---

### IPv6 Addressing

IPv6 uses 128-bit addresses written in hexadecimal notation.

Example:

2001:db8:0000:0000:de10:1234

IPv6 was created to overcome IPv4 address exhaustion and provides a vastly larger address space.

Important IPv6 concepts:

* Global addresses
* Link-local addresses
* Prefix notation
* Stateless Address Auto Configuration (SLAAC)

---

### Public and Private Addressing

Private addresses are used within local networks and are not routable across the public internet.

Public addresses are assigned by Internet Service Providers (ISPs) and allow communication across the internet.

Network Address Translation (NAT) is used to translate private addresses into public addresses when accessing internet resources.

---

### Default Gateway

A default gateway is the router interface used to forward traffic to destinations outside the local network.

If a destination is not part of the local subnet, traffic is forwarded to the configured gateway for routing.

---

### DHCP (Dynamic Host Configuration Protocol)

DHCP automatically provides network configuration information to clients, including:

* IP address
* Subnet mask
* Default gateway
* DNS server addresses

The DHCP process follows four stages:

1. DHCP Discover
2. DHCP Offer
3. DHCP Request
4. DHCP Acknowledgement (ACK)

DHCP leases allow addresses to be assigned temporarily and renewed automatically.

---

### DNS (Domain Name System)

DNS translates human-readable host names into IP addresses.

Example:

[www.google.com](http://www.google.com) → IP Address

DNS uses a hierarchical structure:

* Root Domain
* Top-Level Domain (TLD)
* Second-Level Domain
* Subdomain

Common DNS resource records include:

* A Record (IPv4)
* AAAA Record (IPv6)
* CNAME
* MX
* TXT
* SPF
* DKIM
* DMARC

---

### TCP and UDP

#### TCP (Transmission Control Protocol)

TCP is a connection-oriented protocol designed for reliable communication.

Features:

* Three-way handshake
* Sequence numbers
* Acknowledgements
* Error checking
* Retransmission of lost packets

Common uses:

* HTTPS
* SSH
* Email
* File transfers

#### UDP (User Datagram Protocol)

UDP is connectionless and prioritizes speed over reliability.

Features:

* No acknowledgements
* Lower overhead
* Faster transmission

Common uses:

* Voice communication
* Video streaming
* Real-time applications

---

### Common Network Protocols

| Port    | Protocol | Purpose                     |
| ------- | -------- | --------------------------- |
| 20/21   | FTP      | File Transfer               |
| 22      | SSH      | Secure remote access        |
| 23      | Telnet   | Remote access (unencrypted) |
| 25      | SMTP     | Email transfer              |
| 53      | DNS      | Name resolution             |
| 67/68   | DHCP     | Dynamic addressing          |
| 80      | HTTP     | Web traffic                 |
| 110     | POP3     | Email retrieval             |
| 137-139 | NetBIOS  | Windows networking          |
| 143     | IMAP     | Email access                |
| 389     | LDAP     | Directory services          |
| 443     | HTTPS    | Secure web traffic          |
| 445     | SMB      | Windows file sharing        |
| 3389    | RDP      | Remote Desktop              |

---

### VLANs (Virtual LANs)

VLANs logically separate devices on the same physical switch into different broadcast domains.

Benefits:

* Improved security
* Better network organization
* Reduced broadcast traffic
* Easier traffic management

Each VLAN operates as an independent network and typically requires its own subnet.

---

### VPNs (Virtual Private Networks)

VPNs create encrypted tunnels across public networks.

Benefits:

* Secure remote access
* Protection of data in transit
* Secure communication across untrusted networks

VPNs are commonly used by remote workers to access organizational resources securely.

---

## Key Takeaways

* IP addressing identifies devices and networks.
* Subnet masks determine network and host boundaries.
* NAT allows private devices to access public networks.
* DHCP automates network configuration.
* DNS translates host names into IP addresses.
* TCP prioritizes reliability, while UDP prioritizes speed.
* Common protocols rely on well-known port numbers.
* VLANs improve segmentation and security.
* VPNs provide secure communication over the internet.
* IPv6 is the long-term replacement for IPv4.

---

## Reflection

This module significantly improved my understanding of how modern networks function. Before studying these topics, I knew that devices communicated using IP addresses, but I did not fully understand how addressing, routing, DNS, DHCP, and transport protocols worked together.

The sections on DHCP, DNS, TCP/UDP, and common ports helped me understand the practical side of networking and how services communicate across networks. Learning about VLANs and VPNs also showed how organizations improve security and manage large networks efficiently.

This module reinforced the importance of networking fundamentals because nearly every area of IT and cybersecurity depends on understanding how devices communicate. The concepts covered here will be essential as I continue studying A+, Network+, Security+, and future cybersecurity topics.
