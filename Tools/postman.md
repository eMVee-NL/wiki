Postman
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Download
------
Postman is an awesome application to test API functionalities.
[Download Postman](https://www.postman.com/downloads/) from Postman Inc. Choose the application which fits to your system.

Install
------
Open the CLI and navigate to the directory where you just saved the Postman Download.
To install Postman run the following command on your Kali machine to extract:

```bash
sudo rm -rf /opt/Postman/
sudo tar xvf Postman-<your version>.tar.gz -C /opt/
sudo ln -sf /opt/Postman/app/Postman /usr/bin/postman
```

Replace the 'your version' with the version of the file which you have downloaded to your machine.

Run Postman
------
Type in the start panel Postman and hit enter if "Run Postman" is shown.




Installation script (not tested)
------

```bash
#!/bin/bash
cd /tmp || exit
echo "Downloading Postman ..."
wget -q https://dl.pstmn.io/download/latest/linux?arch=64 -O postman.tar.gz
tar -xzf postman.tar.gz
rm postman.tar.gz

echo "Installing to opt..."
if [ -d "~/Postman" ];then
    rm -rf ~/Postman
fi
mv Postman ~/Postman

echo "Creating symbolic link..."
if [ -L "/usr/bin/postman" ];then
    sudo rm -f /usr/bin/postman
fi
sudo ln -s ~/Postman/Postman /usr/bin/postman

echo "Installation completed successfully."
echo "You can use Postman!"
```