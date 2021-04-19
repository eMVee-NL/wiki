Visual Studio
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__

Download
------
Visual Studio is a great application to develop applications and/or scripts and it can be used on Linux as well.
[Download Visual Studio](https://code.visualstudio.com/) from Microsoft. Choose the application which fits to your system.

Install
------
Open the CLI and navigate to the directory where you just saved the Visual Studio Download.
To install Visual Studio run the following command on your Kali machine:

```bash
sudo apt install ./<file>.deb
```

Replace the '<file>' with the name of the file which you have downloaded to your machine.

Run Visual Studio
------
To start Visual Studio, you can open the start panel and type Visual Studio. But it is possible to run the application from the CLI as well.
To start Visual Studio from the command line just follow the example:

```bash
code filename.sh
```

Visual studio will create the file filename.sh if it does not exist, otherwise it will open the file.

Turn off the telemetry settings
------
Micrsoft wants to collect some data to improve their product. Something which could be okay if you want to help and you choose to help them.
In this case you have to choose to opt out. This can be done via the settings screen in Visual Studio.
Click on 'File' -> 'Preferences' -> 'Settings' 
![Post variables](../img/visual-studio/settings-telemetry1.png?raw=true "Open settings Visual Studio")

Now search for 'Telemetry' in the searchbar and disable all boxes.
![Post variables](../img/visual-studio/settings-telemetry2.png?raw=true "Disable 'Telemetry' settings in Visual Studio")


