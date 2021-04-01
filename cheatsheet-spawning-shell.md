Spawning shell cheatsheet
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Python
---------
```bash
python -c 'import pty; pty.spawn("/bin/sh")'
```

Bash
---------
```bash
echo os.system('/bin/bash')
```


Vi
---------
From within vi it could be possible to breakout a restricted shell..
```bash
#(From within vi)
:!bash
```

nmap
---------
It could be possible to breakout a restricted shell with an interactive nmap
```bash
nmap -i
```