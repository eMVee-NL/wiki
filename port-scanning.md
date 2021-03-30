Port scanning
=======

Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.

Massscan
---------
Massscan is a CLI tool which can be used to enumerate the ports which are open on a target.

```bash
$ sudo masscan -p 1-65535 10.10.10.30 -e tun0 --rate=1000
[sudo] password for user: 
Starting masscan 1.3.2 (http://bit.ly/14GZzcT) at 2021-03-21 10:09:24 GMT
Initiating SYN Stealth Scan
Scanning 1 hosts [65535 ports/host]
Discovered open port 636/tcp on 10.10.10.30                                    
Discovered open port 49676/tcp on 10.10.10.30
---snip--   
```

nmap
---------
nmap can be used to identify open ports, running services on those ports and even the Operating System of the target(s). This tool has a lot of options which can be used.
In this part we will describe a very basic usage, otherwise we have to write a whole book. 

sudo nmap -sS -A $ip
[sudo] password for user
Starting Nmap 7.91 ( https://nmap.org ) at 2021-03-21 10:23 CET
Nmap scan report for 10.10.10.27
Host is up (0.025s latency).
Not shown: 996 closed ports
PORT     STATE SERVICE      VERSION
135/tcp  open  msrpc        Microsoft Windows RPC
139/tcp  open  netbios-ssn  Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds Windows Server 2019 Standard 17763 microsoft-ds
1433/tcp open  ms-sql-s     Microsoft SQL Server 2017 14.00.1000.00; RTM
| ms-sql-ntlm-info: 

---snip--


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
| 1433 | MS SQL | TCP |
| 3389 | Remote Desktop Protocol | TCP and UDP |

Ports
---------
There are 65535 ports which can be used on a computer. Those ports can be devided in: Well-known ports, Registered ports and Dynamic, private or ephemeral ports.
https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers

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
