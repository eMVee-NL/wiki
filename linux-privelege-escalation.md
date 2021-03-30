

Shows the Linux kernel
┌──(qubes㉿crowbar)-[~]
└─$ uname -a         
Linux crowbar 5.10.0-kali3-amd64 #1 SMP Debian 5.10.13-1kali1 (2021-02-08) x86_64 GNU/Linux

Whows the release version of the distro                                                                             
┌──(qubes㉿crowbar)-[~]
└─$ lsb_release -a                                                  
No LSB modules are available.
Distributor ID: Kali
Description:    Kali GNU/Linux Rolling
Release:        2021.1
Codename:       kali-rolling

shows the version of the device manager
┌──(qubes㉿crowbar)-[~]
└─$ udevadm --version
247

Finding an exploit.                                                                             
┌──(qubes㉿crowbar)-[~]
└─$ searchsploit udev   
------------------------------------------- ---------------------------------
 Exploit Title                             |  Path
------------------------------------------- ---------------------------------
Linux Kernel 2.6 (Debian 4.0 / Ubuntu / Ge | linux/local/8478.sh
Linux Kernel 2.6 (Gentoo / Ubuntu 8.10/9.0 | linux/local/8572.c
Linux Kernel 4.8.0 UDEV < 232 - Local Priv | linux/local/41886.c
Linux Kernel UDEV < 1.4.1 - 'Netlink' Loca | linux/local/21848.rb
------------------------------------------- ---------------------------------
Shellcodes: No Results


Check the bash history
cat ~/.bash_history

Check all the directories and file under /home
ls -ahlR /home