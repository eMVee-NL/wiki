Port scanning
=======

Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.

nmap
---------
nmap can be used to identify open ports and running services on those ports.

Common ports
---------

| Port 	        | Service name 	| Transport protocol |
| ------------- |:-------------:|:------------------:|
| 20, 21 | File Transfer Protocol (FTP) | TCP |
| 22 |Secure Shell (SSH) 	 | TCP and UDP| 
| 23 | Telnet | TCP |
| 25 | Simple Mail Transfer Protocol (SMTP) | TCP
| 50, 51 | IPSec |
| 53 | Domain Name System (DNS) | TCP and UDP |
| 67, 68 | Dynamic Host Configuration Protocol (DHCP) | UDP |
| 69 | Trivial File Transfer Protocol (TFTP) | UDP |
| 79 | Finger | TCP and UDP |
| 80 | HyperText Transfer Protocol (HTTP) | TCP |
| 110 | Post Office Protocol (POP3) | TCP |
| 119 | Network News Transport Protocol (NNTP) | TCP |
| 123 | Network Time Protocol (NTP) | UDP |
| 135-139 | NetBIOS | TCP and UDP |
| 143 | Internet Message Access Protocol (IMAP4) | TCP and UDP |
| 161, 162 | Simple Network Management Protocol (SNMP) | TCP and UDP |
| 389 | Lightweight Directory Access Protocol (LDAP) | TCP and UDP |
| 443 | HTTP with Secure Sockets Layer (SSL) | TCP and UDP |
| 989, 990 | FTP over SSL/TLS (implicit mode) | TCP |
| 3389 | Remote Desktop Protocol | TCP and UDP |

Ports
---------

| Port number   | service       |
| ------------- |:-------------:|
| 1             | tcpmux        |
| 2             | tcpmux        |
| 3             |               | 
| 4             |               | 
| 5             |               | 
| 6             |               | 
| 7             |               | 
| 8             |               | 
| 9             |               | 
| 10            |               | 
| 11            |               | 
| 12            |               | 
| 13            |               | 
| 14            |               | 
| 15            |               | 
| 16            |               | 
| 17            |               | 
| 18            |               | 
| 19            |               | 
| 20            | FTP           | 
| 21            | FTP           | 
| 22            | SSH           | 
| 23            | Telnet        | 
| 24            |               | 
| 25            | SMTP          | 
| 26            |               | 
| 27            |               | 
| 28            |               | 
| 29            |               | 
| 30            |               | 
| 31            |               | 
| 32            |               | 
| 33            |               | 
| 34            |               | 
| 35            |               | 
| 36            |               | 
| 37            |               | 
| 38            |               | 
| 39            |               | 
| 40            |               | 
| 41            |               | 
| 42            |               | 
| 43            |               | 
| 44            |               | 
| 45            |               | 
| 46            |               | 
| 47            |               | 
| 48            |               | 
| 49            |               | 
| 50            |               | 
| 51            |               | 
| 52            |               | 
| 53            | DNS           | 
| 54            |               | 
| 55            |               | 
| 56            |               | 
| 57            |               | 
| 58            |               | 
| 59            |               | 
| 60            |               | 
| 61            |               | 
| 62            |               | 
| 63            |               | 
| 64            |               | 
| 65            |               | 
| 66            |               | 
| 67            | DHCP          | 
| 68            | DHCP          | 
| 69            | TFTP          | 
| 70            |               | 
| 71            |               | 
| 72            |               | 
| 73            |               | 
| 74            |               | 
| 75            |               | 
| 76            |               | 
| 77            |               | 
| 78            |               | 
| 79            | Finger        | 
| 80            | http          | 
