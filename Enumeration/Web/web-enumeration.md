Web enumeration
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Directory enumeration
---------
Websites often have multiple (sub)directories available. To identify those directories it is possible to enumerate them with bruteforcing or by using [wordlists](../../Passwords/wordlists.md).

  * [Dirb](dirb.md)
  * [Dirbuster](dirbuster.md)
  * [Dirsearch](dirsearch.md)
  * [Gobuster](gobuster.md)
  * [Wfuzz](wfuzz.md)
  * [Amass](amass.md)
  * [Sublist3r](sublist3r.md)

Technologies used
---------
Websites can use several technologies, while pentesting this can be an advanced for exploiting the website.
 
  * whatweb
  * Wappalyzer
  
__whatweb__
whatweb can be used via the CLI to identify technologies running on the website.
```bash
whatweb -u http://www.example.com
```

__Wappalyzer__
Wappalyzer is an [add-on in Firefox](https://addons.mozilla.org/en-US/firefox/addon/wappalyzer/) which can indicate the technologies used on the website.

CMS
---------
A content management system (CMS) is a computer software used to manage the creation and modification of digital content.
CMSs are typically used for enterprise content management (ECM) and web content management (WCM). ECM typically supports multiple users in a collaborative environment by integrating document management, digital asset management, and record retention. Alternatively, WCM is the collaborative authoring for websites and may include text and embed graphics, photos, video, audio, maps, and program code that display content and interact with the user. ECM typically includes a WCM function.   
    
__Wordpress - WPSCAN__
Wordpress is one of the most used CMS on the internet and can be enumerated with WPSCAN.
```bash
wpscan -u http://www.example.com -e u
```


__Drupal - DROOPSCAN__
Drupal is a CMS which can be enumerated with DROOPSCAN.
```bash
droopscan -u http://www.example.com -e u
```
__Joomla - JOOMSCAN__
Joomla is a CMS which can be enumerated with JOOMSCAN.
```bash
joomscan -u http://www.example.com -e u
```
Vulnerability scan
---------
When a webserver is running it is possible to identify vulnerabilities with
  
  * [Nikto](nikto.md)
  * OWASP ZAP

WebDAV
--------
WebDAV (Web Distributed Authoring and Versioning) is an extension of the Hypertext Transfer Protocol (HTTP) that allows clients to perform remote Web content authoring operations. 
Cadaver is a tool which can be used to authenticate and upload files to the web server.
```bash
cadaver http://www.example.com/webdav
```


Local File Inclusion - LFI
--------
**Linux**
../../../../../etc/passwd
**Windows**
../../../../../../boot.ini
../../../../../../WINDOWS/system32/config/sam
../../../../../../WINDOWS/system32/repair/system
../../../../../../WINDOWS/system32/repair/sam