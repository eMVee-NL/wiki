OpenVAS
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__


OpenVAS is an opensource security scanner it started as a fork of Nessus which went from an opensource project to a closed source scanner.

Install OpenVAS
---------
Run the update and upgrade command in the CLI before starting the installation. As seconds step make sure that [haveged](https://www.issihosts.com/haveged/) is running. This is needed during the setup to create an encryption key. To create this key it’s important to have enough random data available. 

```bash
┌──(user@kali)-[~]
└─$ ps aux | grep -i have
root         418  0.0  0.0   8120  5304 ?        Ss   20:30   0:00 /usr/sbin/haveged --Foreground --verbose=1
user       2064  0.0  0.0   6312   656 pts/0    S+   20:36   0:00 grep --color=auto -i have
```

**Before starting, be aware that the complete installation till the end could take a while before it is finished.**

```bash
sudo apt install openvas -y
```

**Check for Redis.**
OpenVAS uses its own redis service on Kali. This redis service is configured to work with OpenVAS correctly. Just check with the following command the status of Redis.
```bash
systemctl status redis-server@openvas.service
```

Since a while age the openvas-setup installation script has been renamed to gvm-setup. GVM stands for Greenbone Vulnerability Manager, so probably it will be renamed in the future.The installation script will set the PostgreSQL database, create an admin user with a generated password, download and import all the SCAP data. To run the installation you should be root. See the example below.

```bash                    
┌──(user@kali)-[~]
└─$ sudo su                                                                                           
┌──(root@kali)-[/home/user]
└─$ gvm-setup
---snip---
sent 711 bytes  received 74,427,735 bytes  407,827.10 bytes/sec
total size is 74,407,669  speedup is 1.00
[*] Checking Default scanner
08b69003-5fc2-4037-a479-93b440211c73  OpenVAS  /var/run/ospd/ospd.sock  0  OpenVAS Default

[+] Done
[*] Please note the password for the admin user
[*] User created with password 'GENERATED-PASSWORD'.

```
**<ins>Keep this password somewhere safe!<ins>**

After the installation verify that the installation was succesfully installed on the system. In the example below it is shown how to verify this via the CLI.

```bash
┌──(user@kali)-[~]
└─$ sudo gvm-check-setup 
[sudo] password for kali: 
gvm-check-setup 20.8.0
  Test completeness and readiness of GVM-20.8.0
Step 1: Checking OpenVAS (Scanner)...
---snip---
It seems like your GVM-20.8.0 installation is OK.
```

Reset your admin password
----------

After the installation (or during at the end of the installation) the script will display the generated password for the admin account. If you have forgotten this password (probably you didn't write it down, or stored it in a password manager), you can reset the admin password. The password reset has to be done via the CLI with an argument. This means that this new password is kept in your history. It is recommended to use a shell without history memory or you have to clear the history after updating your new admin password. In the example below the command is show to reset a password and clear the history via the CLI.
 
```bash
 su - _gvm -s /bin/sh -c "gvmd --user=admin --new-password SUPER-NEW-PASSWORD; history -c"
 history -c
```


Keep OpenVAS up-to-date
----------
Over time, OpenVAS must be updated with the latest data so that the scanner will recognize new vulnerabilities. Therefore, update this information regularly by running the gvm-feed-update command. 

```bash
sudo gvm-feed-update
```

Start OpenVAS
----------
Starting OpenVAS oon your machine is pretty easy. You have to run thw following command in the CLI.
```bash
┌──(user@kali)-[~]
└─$ sudo gvm-start   
```

After running the command, OpenVAS should run on your machine.
Open your browser and navigate to this URL: [https://127.0.0.1:9392](https://127.0.0.1:9392). It should open with the logon webpage for OpenVAS.
![Post variables](/img/openvas/logon.png?raw=true "OpenVAS logon webpage")