Scanning on IP addresses
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

arp-scan
---------

```bash
arp-scan 192.168.10.0/24
```

Netdiscover
---------

```bash
netdiscover -r 192.168.10.0/24
```

fping
---------
fping is a tool designed to send ICMP echo requests to multiple systems. In the example below fping is scanning a local network with the -aeg flag as parameter.
This means fping shows host that are alive, sows the elapsed time and it generates a list of the targets based on the address block.

```bash
fping -aeg 192.168.10.0/24
```

hping3
---------


ping
---------
Ping is another CLI tool to send ICMP echo request. There is a difference between the ping in Linux and in Windows. In Windows it will automatically stop after 4 requests. In Linux it will continues send ICMP echo request until it is stopped or if the parameter -c for count is given.
In the example below we send 3 ICMP echo requests to a local IP address.
```bash
export ip=10.10.10.27  
                                                                             
ping -c3 $ip
PING 10.10.10.27 (10.10.10.27) 56(84) bytes of data.
64 bytes from 10.10.10.27: icmp_seq=1 ttl=127 time=24.2 ms
64 bytes from 10.10.10.27: icmp_seq=2 ttl=127 time=25.1 ms
64 bytes from 10.10.10.27: icmp_seq=3 ttl=127 time=27.3 ms

--- 10.10.10.27 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2003ms
rtt min/avg/max/mdev = 24.150/25.497/27.252/1.298 ms

```

nmap
---------
Nmap is a known application with a lot of options to scan networks, identifying hosts, open ports, running service and even vulnerabilities. In this section nmap is used to perform a ping sweep.
Nmap “ping sweep” is a method to discover connected devices in a network using the nmap security scanner, for a device to be discovered we only need it to be turned on and connected to the network. We can tell nmap to discover all devices in the network or define ranges.
```bash
nmap  -sP 172.31.1-255.1-255
```