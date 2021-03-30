Gobuster
=======

Gobuster is a CLI tool and can be used to enumerate directories on a webserver.

Usage
---------
gobuster whould be started with a few parameters.
>  dir         Uses directory/file enumeration mode
>  dns         Uses DNS subdomain enumeration mode
>  fuzz        Uses fuzzing mode
>  -u          for the URL as target
>  -w          for the wordlist which should be used




```bash
gobuster dir -u http://www.example.com -w /usr/share/wordlists/dirb/common.txt
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://www.example.com 
[+] Method:                  GET
[+] Threads:                 10
[+] Wordlist:                /usr/share/wordlists/dirb/common.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Timeout:                 10s
===============================================================
2021/03/21 10:52:35 Starting gobuster in directory enumeration mode
===============================================================
/wordpress            (Status: 301) [Size: 152] [--> http://www.example.com/wordpress/]
                                                                                   
===============================================================
2021/03/21 10:52:49 Finished
===============================================================
```