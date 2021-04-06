Wordlists
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__



Default wordlists on Kali
---------
On Kali there are default wordlist available after the installation.
Those wordlist can be found here: 
> /usr/share/wordlists

The most known wordlists is the 'rockyou' file. After installation, this file is in a compressed file which should be extracted before you can use it.
To extract rockyou.txt.gz you should enter the following command in the terminal.
```bash
sudo gzip -d rockyou.txt.gz 
``` 
Or you can use gunzip in the terminal.
```bash
sudo gunzip rockyou.txt.gz
```

There are several directories with wordlists present.
 
  * dirb
  * dirbuster
  * seclists
  * wfuzz


SecList - Daniel Miessler
---------
> SecLists is the security tester's companion. It's a collection of multiple types of lists used during security assessments, collected in one place. List types include usernames, passwords, URLs, sensitive data patterns, fuzzing payloads, web shells, and many more. The goal is to enable a security tester to pull this repository onto a new testing box and have access to every type of list that may be needed.

Get SecList from [Github](https://github.com/danielmiessler/SecLists).

If you are working on Kali, you can install it via the terminal.
```bash
sudo apt -y install seclists
```

If it's not on your machine and you are not working with Kali, clone it to your machine.
```bash
git clone https://github.com/danielmiessler/SecLists.git
```