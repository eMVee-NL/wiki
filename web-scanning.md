Webscanning
=======

Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.

Directory enumeration
---------
Websites often have multiple (sub)directories available. To identify those directories it is possible to enumerate them with bruteforcing and wordlists.

  * Dirb
  * Dirbuster
  * Dirsearch
  * Gobuster
  * Wfuzz

Technologies used
---------
Websites can use several technologies, while pentesting this can be an advanced for exploiting the website.
  * whatweb
  * Wappalyzer

__whatweb__
whatweb can be used via the CLI to identify technologies running on the website.


__Wappalyzer__
Wappalyzer is an add-on in Firefox which can indicate the technologies used on the website.

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

__Joomla - JOOMSCAN__

Vulnerability scan
---------
![](http://placekitten.com/g/800/800)
The above image floats left to this text.
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
[...]
