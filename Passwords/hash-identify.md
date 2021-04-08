Identify a hash
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__


There are several types of hashes which should or could be identified befor trying to crack them.
On Kali there is default an application (Hash-identifier) available to identify those hashes.

Hash-identifier
---------
To identify a hash the application can be starterd via the terminal.
```bash
─$ hash-identifier
   #########################################################################
   #     __  __                     __           ______    _____           #
   #    /\ \/\ \                   /\ \         /\__  _\  /\  _ `\         #
   #    \ \ \_\ \     __      ____ \ \ \___     \/_/\ \/  \ \ \/\ \        #
   #     \ \  _  \  /'__`\   / ,__\ \ \  _ `\      \ \ \   \ \ \ \ \       #
   #      \ \ \ \ \/\ \_\ \_/\__, `\ \ \ \ \ \      \_\ \__ \ \ \_\ \      #
   #       \ \_\ \_\ \___ \_\/\____/  \ \_\ \_\     /\_____\ \ \____/      #
   #        \/_/\/_/\/__/\/_/\/___/    \/_/\/_/     \/_____/  \/___/  v1.2 #
   #                                                             By Zion3R #
   #                                                    www.Blackploit.com #
   #                                                   Root@Blackploit.com #
   #########################################################################
--------------------------------------------------
 HASH: 8743b52063cd84097a65d1633f5c74f5

Possible Hashs:
[+] MD5
```

Identify hash online
---------

Warning: Only use those websites for compromised hashes during a CTF event or a vulnerable machine in a lab environment.

[Suip.biz](https://suip.biz/?act=hashtag) is a online hash identifier. Use this only for hashesh found during a CTF event and during this event the offline versions are not sufficient enough.