Nikto
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Nikto is a free software command-line vulnerability scanner that scans webservers for dangerous files/CGIs, outdated server software and other problems. It performs generic and server type specific checks. It also captures and prints any cookies received. This tool is default installed on Kali.

Default scan
---------
To start a simple scan on a webserver you need to specify the host (target) with the -h flag as shown in the example below. Default it will scan on port 80.
```bash
nikto -h http://www.example.com
```

Other port
---------
A website is not always running on the default port, so we need to specify the port in the scan request. In this case we can specify it in two ways.
```bash
nikto -h 192.168.0.1 -p 443
```
Or you could specify it like this:
```bash
nikto -h https://192.168.0.1:443/
```

Multiple ports
---------
In certain circumstainces multiple webservers are running on different ports. In this situation we scan with Nikto multiple ports at once.
```bash
nikto -h 192.168.0.1 -p 80,443,8080,8443
```