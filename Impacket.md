Impacket
=======
Impacket is developed by [Secureauth](https://www.secureauth.com/labs/open-source-tools/impacket/) and released on [Github](https://github.com/SecureAuthCorp/impacket).


Installation
---------
Impacket is by default not installed on Kali. To use this tool we have to install it on our computer.

```bash
$ sudo apt install python3-pip -y
$ sudo git clone https://github.com/SecureAuthCorp/impacket.git 
$ sudo pip3 install .
$ sudo python3 ./setup.py install
```

Remote Execution
---------

* psexec.py: PSEXEC like functionality example using RemComSvc (https://github.com/kavika13/RemCom).
* smbexec.py: A similar approach to PSEXEC w/o using RemComSvc. The technique is described here. Our implementation goes one step further, instantiating a local smbserver to receive the output of the commands. This is useful in the situation where the target machine does NOT have a writeable share available.
* atexec.py: This example executes a command on the target machine through the Task Scheduler service and returns the output of the executed command.
* wmiexec.py: A semi-interactive shell, used through Windows Management Instrumentation. It does not require to install any service/agent at the target server. Runs as Administrator. Highly stealthy.
* dcomexec.py: A semi-interactive shell similar to wmiexec.py, but using different DCOM endpoints. Currently supports MMC20.Application, ShellWindows and ShellBrowserWindow objects.

Kerberos
---------

Windows Secrets
---------

Server Tools/MiTM Attacks
---------

WMI
---------

Known Vulnerabilities
---------

SMB/MSRPC
---------

MSSQL / TDS
---------

File Formats
---------

Other
---------