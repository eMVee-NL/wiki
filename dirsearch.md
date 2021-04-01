Dirsearch
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Installation
---------
Run the following command to clone dirsearch to your local machine
```bash
git clone https://github.com/maurosoria/dirsearch.git
cd dirsearch
pip3 install -r requirements.txt
```

Usage
---------
Dirsearch is a Python CLI application which should be run with a few arguments.

> -u = URL
> -e = Extension
> -w = Wordlist

```bash
python3 dirsearch.py -u http://www.example.com -e htm,html,txt,php
```


