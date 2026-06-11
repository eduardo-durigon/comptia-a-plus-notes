# Module 7 – Supporting Network Services

## What I Studied

This module focused on the network services, servers, and infrastructure components that support communication, resource sharing, authentication, monitoring, and security across modern networks. I learned how organizations use different types of servers to provide services such as file sharing, web hosting, email delivery, remote administration, network monitoring, and centralized authentication.

The module also introduced security appliances, embedded systems, Internet of Things (IoT) devices, and common network troubleshooting methodologies used to diagnose connectivity and performance issues.

The module covered:

* File and print servers
* SMB and CIFS file sharing
* FTP, FTPS, and SFTP
* Database servers
* Web servers and web applications
* HTTP and HTTPS
* SSL/TLS and digital certificates
* Mail servers and email protocols
* LDAP and directory services
* AAA, RADIUS, and TACACS+
* Remote access technologies
* SSH, Telnet, and RDP
* NTP time synchronization
* SNMP and Syslog monitoring
* Proxy servers
* Unified Threat Management (UTM)
* IDS and IPS technologies
* Load balancers
* Legacy systems
* Embedded systems and SCADA
* Internet of Things (IoT)
* Wired and wireless network troubleshooting
* VoIP troubleshooting
* Limited connectivity troubleshooting

## Related Lab

🔗 **Associated Lab:**

https://github.com/eduardo-durigon/endpoint-troubleshooting-labs-2026/tree/main/lab06-module7-supporting-network-services

This hands-on lab demonstrates the networking services and troubleshooting concepts covered throughout Module 7.

---

## Key Concepts

### File and Print Servers

File servers provide centralized storage that allows users to access shared files across a network. Print servers manage printers and print jobs, helping organizations efficiently control printing resources.

Common file-sharing technologies include:

* SMB (Server Message Block)
* CIFS (Common Internet File System)
* FTP-based file sharing

Modern Windows networks primarily use SMB for file and printer sharing.

---

### SMB and Network File Sharing

SMB is the protocol used by Windows systems to share files, folders, and printers across networks.

Important concepts:

* SMB operates over TCP port 445
* SMBv3 is the current version
* SMBv1 contains significant security vulnerabilities and is generally disabled
* Linux systems commonly support SMB through Samba

SMB remains one of the most important protocols in enterprise environments.

---

### FTP, FTPS, and SFTP

File Transfer Protocol (FTP) allows clients to upload and download files from remote servers.

FTP characteristics:

* Uses TCP port 21
* Transfers data in plain text
* Considered insecure for modern environments

Secure alternatives include:

* FTPS (FTP over TLS)
* SFTP (SSH File Transfer Protocol)

SFTP is the most commonly used secure file transfer solution today.

---

### Database Servers

Database servers store, organize, and manage large amounts of data.

Common database types include:

#### Relational Databases

Store information in tables using rows and columns.

Examples:

* Oracle
* MySQL
* MariaDB

These databases commonly use SQL (Structured Query Language).

#### Non-Relational Databases

Store data using flexible structures such as documents, graphs, or key-value pairs.

Examples:

* MongoDB
* CouchDB
* Amazon SimpleDB

These systems are often used for large-scale and highly flexible applications.

---

### Web Servers and HTTP

Web servers provide websites and web applications to clients using HTTP and HTTPS.

HTTP characteristics:

* Uses TCP port 80
* Supports client requests such as GET and POST
* Delivers web pages, images, and other resources

URLs identify internet resources and typically contain:

* Protocol
* Host name (FQDN)
* Resource path

---

### HTTPS, TLS, and Digital Certificates

HTTPS secures web communications through encryption.

Key concepts:

* HTTPS uses TCP port 443
* TLS evolved from SSL
* Digital certificates verify server identity
* Public and private key pairs establish encrypted sessions

HTTPS protects data from interception and tampering while providing authentication of web servers.

---

### Mail Servers and Email Protocols

Email communication relies on several protocols.

#### SMTP (Simple Mail Transfer Protocol)

Used for sending email.

Common ports:

* TCP 25
* TCP 587 (secure message submission)

#### POP3

Downloads email from a mailbox server to a client device.

Ports:

* TCP 110
* TCP 995 (secure)

#### IMAP

Allows users to manage email directly on the server.

Ports:

* TCP 143
* TCP 993 (secure)

IMAP is generally preferred because it supports synchronization across multiple devices.

---

### Directory Services and LDAP

Directory services maintain centralized information about users, devices, and network resources.

LDAP (Lightweight Directory Access Protocol):

* Uses TCP/UDP port 389
* Queries and manages directory information

LDAPS:

* Uses TCP port 636
* Adds encryption through TLS

Microsoft Active Directory is one of the most widely used directory services in enterprise networks.

---

### AAA, RADIUS, and TACACS+

AAA stands for:

* Authentication
* Authorization
* Accounting

AAA systems centralize access control and logging.

Common protocols:

#### RADIUS

* Uses UDP ports 1812 and 1813
* Commonly used for user authentication

#### TACACS+

* Uses TCP port 49
* Commonly used for network device administration

These systems support centralized management and Single Sign-On (SSO) environments.

---

### Remote Access Technologies

Remote administration allows users and administrators to access systems across networks.

#### SSH

* TCP port 22
* Secure remote command-line access
* Supports encrypted communication

#### Telnet

* TCP port 23
* Unencrypted
* Considered insecure

#### RDP (Remote Desktop Protocol)

* TCP port 3389
* Provides graphical remote desktop access
* Commonly used in Windows environments

---

### Time Synchronization and Monitoring

#### NTP (Network Time Protocol)

Synchronizes clocks across network devices.

Key concepts:

* Uses UDP port 123
* Supports stratum levels
* Ensures accurate timestamps for logs and security events

#### SNMP (Simple Network Management Protocol)

Used for monitoring network devices.

Common ports:

* UDP 161
* UDP 162

SNMP enables administrators to monitor device health and performance.

#### Syslog

Collects logs from multiple devices into a centralized system.

Benefits include:

* Easier monitoring
* Faster troubleshooting
* Better incident response

---

### Proxy Servers

A proxy server receives requests from clients and forwards them to external resources.

Benefits:

* Content filtering
* Security enforcement
* Bandwidth reduction through caching
* Access control

Proxy servers are frequently used to manage internet access in organizations.

---

### Unified Threat Management (UTM)

UTM appliances combine multiple security technologies into a single platform.

Common features include:

* Firewalls
* IDS/IPS
* Anti-malware scanning
* Content filtering
* Spam filtering
* Data Loss Prevention (DLP)

UTM solutions simplify security management and reporting.

---

### Load Balancers

Load balancers distribute client requests across multiple servers.

Benefits:

* High availability
* Improved performance
* Scalability
* Fault tolerance

They are commonly used for web applications and enterprise services.

---

### Legacy Systems

Legacy systems are platforms that are no longer actively supported by vendors.

Risks include:

* Lack of security updates
* Unsupported software
* Increased vulnerability exposure

Organizations often isolate legacy systems to reduce security risks.

---

### Embedded Systems, ICS, and SCADA

Embedded systems perform dedicated functions within specialized devices.

Industrial environments commonly use:

* PLCs (Programmable Logic Controllers)
* HMIs (Human-Machine Interfaces)
* ICS (Industrial Control Systems)
* SCADA (Supervisory Control and Data Acquisition)

These technologies are critical for infrastructure such as power, water, transportation, and manufacturing systems.

---

### Internet of Things (IoT)

IoT devices combine sensors, software, and network connectivity to exchange data.

Examples include:

* Smart thermostats
* Smart cameras
* Smart speakers
* Home automation systems

Because IoT devices are connected to networks, they introduce additional security considerations and attack surfaces.

---

### Network Troubleshooting

The module also introduced structured troubleshooting methodologies for network issues.

Common troubleshooting areas included:

#### Wired Connectivity

* Faulty cables
* Damaged ports
* NIC failures
* Duplex mismatches
* Port flapping

#### Wireless Connectivity

* Weak signal strength
* RF interference
* Channel congestion
* Authentication failures
* SSID configuration issues

#### VoIP Troubleshooting

Key performance factors:

* Latency
* Jitter
* Packet loss
* Quality of Service (QoS)

#### Limited Connectivity

Common causes include:

* DHCP failures
* APIPA addressing (169.254.x.x)
* VLAN misconfiguration
* Gateway issues
* DNS problems

---

## Key Takeaways

* Network services provide the foundation for modern IT operations.
* SMB, FTP, HTTP, and email protocols enable resource sharing and communication.
* HTTPS and TLS protect data through encryption and authentication.
* Directory services centralize user and device management.
* AAA, RADIUS, and TACACS+ strengthen authentication and access control.
* SSH is the preferred method for secure remote administration.
* SNMP and Syslog improve monitoring and troubleshooting capabilities.
* UTM solutions combine multiple security technologies into a centralized platform.
* Legacy systems and IoT devices introduce unique security challenges.
* Structured troubleshooting methodologies help quickly identify network issues.

---

## Reflection

This module gave me a much broader understanding of the services and infrastructure that keep modern networks operating. While Module 6 focused on how devices communicate across networks, this module focused on the systems that provide the services users and administrators rely on every day.

I found the sections on web services, email protocols, directory services, authentication systems, and remote administration particularly valuable because they connected many concepts that I had previously encountered separately. Learning how protocols such as LDAP, RADIUS, SSH, HTTPS, SMTP, IMAP, and SNMP fit into enterprise environments helped me better understand how organizations manage users, devices, and security at scale.

The topics covering UTM appliances, IDS/IPS technologies, embedded systems, SCADA, and IoT also provided a useful introduction to areas that are highly relevant in cybersecurity. Finally, the troubleshooting section reinforced the importance of using a structured approach when diagnosing network issues, whether they involve wired connectivity, wireless performance, VoIP quality, or DHCP-related problems.

Overall, this module strengthened both my networking and cybersecurity foundations and provided a clearer picture of how enterprise networks are designed, managed, monitored, and secured.
