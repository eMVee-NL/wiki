Enumeration techniques and tools
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

NetBIOS enumeration
---------
NetBIOS is an acronym for Network Basic Input/Output System. It provides services related to the session layer of the OSI model allowing applications on separate computers to communicate over a local area network. As strictly an API, NetBIOS is not a networking protocol.
Port number: 137

**Which information could be obtained via NetBIOS?**

  * List of computers that belong to a domain
  * List of shares on the individual hosts in the network
  * Policies and passwords

**Which tools can be used to enumerate on NetBIOS?**

  * nbtstat
  * SuperScan
  * Hyena
  * Winfingerprint

SNMP enumeration
---------
Simple Network Management Protocol is an Internet Standard protocol for collecting and organizing information about managed devices on IP networks and for modifying that information to change device behavior.
Port(s): 161, 162 (Trap)

**Which information could be obtained via SNMP?**

  * Information about network resources such as hosts, routers, devices and shares

**Which tools can be used to enumerate on SNMP?**

  * OpUtils
  * Engineers Toolkit
  * SNMP Scanner

LDAP enumeration
---------
The Lightweight Directory Access Protocol (LDAP) is an open, vendor-neutral, industry standard application protocol for accessing and maintaining distributed directory information services over an Internet Protocol network.
Standard port: 389, 636 (LDAPS)
Secure port: 636

**Which information could be obtained via LDAP?**

  * Valid usernames, addresses, departmental details, groups etc.

**Which tools can be used to enumerate on LDAP?**

  * Softerra LDAP Administrator
  * LDAP Admin Tool

NTP enumeration
---------
The Network Time Protocol (NTP) is a networking protocol for clock synchronization between computer systems over packet-switched, variable-latency data networks. 
Default port: 123 
**Which information could be obtained via NTP?**

  * List of hosts connected to NTP server
  * Clients IP addresses in a network and their system names and OS
  * Internal IPs can also be obtained if the NTP server is in the DMZ

**Which tools can be used to enumerate on NTP?**

  * NTP Server scanner
  * Nmap
  * Wireshark

SMTP enumeration
---------
The Simple Mail Transfer Protocol (SMTP) is an internet standard communication protocol for electronic mail transmission. Mail servers and other message transfer agents use SMTP to send and receive mail messages. 
Standard port: 25, 587, 465
Secure port: 587

**Which information could be obtained via SMTP?**

  * List of users on the SMTP server

**Which tools can be used to enumerate on SMTP?**

  * NetScanTools Pro

IPSEC enumeration
---------
In computing, Internet Protocol Security is a secure network protocol suite that authenticates and encrypts the packets of data to provide secure encrypted communication between two computers over an Internet Protocol network. It is used in virtual private networks.

**Which information could be obtained via IPSEC?**

  * Encryption and hashing algorithm, authentication type, key distribution algorithm, etc.

**Which tools can be used to enumerate on IPSEC?**

  * ike-scan

VoIP enumeration
---------
Voice over Internet Protocol, also called IP telephony, is a method and group of technologies for the delivery of voice communications and multimedia sessions over Internet Protocol networks, such as the Internet.
Port number: 5060 

**Which information could be obtained via VoIP?**

  * VoIP gateway/servers, IP-PBX systems, client software (softphones)/VoIP phones, User-agent IP addresses and user extensions

**Which tools can be used to enumerate on VoIP?**

  * auxiliary/scanner/sip/enumerator

SMB enumeration
---------
In computer networking, Server Message Block (SMB), one version of which was also known as Common Internet File System, is a communication protocol for providing shared access to files, printers, and serial ports between nodes on a network. It also provides an authenticated inter-process communication mechanism. 
Port number: 139 or 445

**Which information could be obtained via SMB?**

  * SMB shares

**Which tools can be used to enumerate on SMB?**

  * NetScan Tools Pro
  * ShareEnum
