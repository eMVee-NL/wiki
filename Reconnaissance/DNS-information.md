DNS Information
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Whois
---------
All domain registars keep records of the domains they are hosting. With the command line tool Whois we can query those domains and gather information about them.
```bash
whois example.com
```

Nslookup
---------
With nslookup we can retrieve the IP address from the Domain Name System (DNS) servers.
```bash
nslookup www.example.com
Server:         XX.XXX.XXX.XXX
Address:        XX.XXX.XXX.XXX#53

Non-authoritative answer:
Name:   www.example.com
Address: XX.XXX.XXX.XX
Name:   www.example.com
Address: XXXX:XXXX:XXX:X:XXX:XXXX:XXOX:XXXX

```
It is even possible to identify the mail servers via nslookup
```bash
nslookup
> set type=mx
> example.com
Server:         XX.XXX.XXX.XXX
Address:        XX.XXX.XXX.XXX#53

Non-authoritative answer:
example.com        mail exchanger = 50 ASPMX3.GOOGLEMAIL.com.
example.com        mail exchanger = 10 ASPMX.L.GOOGLE.com.
example.com        mail exchanger = 30 ALT2.ASPMX.L.GOOGLE.com.
example.com        mail exchanger = 20 ALT1.ASPMX.L.GOOGLE.com.
example.com        mail exchanger = 40 ASPMX2.GOOGLEMAIL.com.
```

Host
---------
Another tool to query DNS is host. 
```bash
host -t ns example.com
example.com name server ns2.xxxxxxxx.com.
example.com name server ns3.xxxxxxxx.com.
example.com name server ns1.xxxxxxxx.com.
```

With host it is possible to perform a **DNS zone transfer** if the DNS server is not configured well.
A zone transfer can be performed as follow:
```bash
host -l example.com ns2.xxxxxxxx.com
```

dig
---------
With dig you are able to gather information about the DNS server. 
```bash
dig example.com
```
It is possible to perform a **DNS zone transfer** if the DNS server is not configured well, just like with host.
```bash
dig axfr @ns2.xxxxxxxx.com domain.name
```

dnsrecon
---------
A zone transfer is generally disallowed and to get more information it is possible to perform a brute foce request.
In the example below dnsrecon is using a wordlist for a brute force scan.

```bash
dnsrecon -d example.com -D /usr/share/wordlists/dnsmap.txt -t brt
[*] Performing host and subdomain brute force against example.com
```