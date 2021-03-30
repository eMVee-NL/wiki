Fluxion
=======

Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.

Fluxion is a security auditing and social-engineering research tool. It is a remake of linset by vk496 with (hopefully) fewer bugs and more functionality. The script attempts to retrieve the WPA/WPA2 key from a target access point by means of a social engineering (phishing) attack. It’s compatible with the latest release of Kali (rolling). Fluxion’s attacks’ setup is mostly manual, but experimental auto-mode handles some of the attacks’ setup parameters.

https://jarnobaselier.nl/fluxion-briljante-evil-twin-wifi-attack/

Installation
---------
Install via CLI
```bash
git clone https://www.github.com/FluxionNetwork/fluxion.git
cd fluxion 
```

Usage
---------
To run
```bash
./fluxion.sh
```