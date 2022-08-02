[<< Main Page](https://supakornpholsiri.github.io/)

# Installing Linux

In this blog I will write about the installation of 3 of linux operating systems : Ubuntu, Debian & MX Linux, via WSL2 and VMware Workstation 16 Player.

### Installing Ubuntu 22.04 LTS with WSL2.
In order to use WSL2. We have to start by downloading Windows Subsystem for Linux Preview from Microsoft store.

![Windows Subsystem for Linux Preview](/assets/images/WSLPreview.png)

You can open Windows Subsystem for Linux Preview now but it won't be useful until we install a distribution.

After that download Ubuntu 22.04 LTS from Microsoft store.

![Ubuntu 22.04 LTS](/assets/images/Ubuntu.png)

Then open the downloaded Ubuntu. This will start the installation of Ubuntu 22.04 LTS, asssuming you have already downloaded Windows Subsystem for Linux Preview.

![Installing Ubuntu](/assets/images/Installing_Ubuntu.png)

Then select you language.

![Language Selecting in Ubuntu](/assets/images/LangSelectUbuntu.png)

Setup your profile.

![Setting up Profile in Ubuntu](/assets/images/SetupProfileUbuntu.png)

You can leave this section as it is and continue.

![Advanced setting in Ubuntu](/assets/images/AdvancedSetupUbuntu.png)

The installation is complete!

![Ubuntu setup completed](/assets/images/SetupCompleteUbuntu.png)

After that you will be greeted with a terminal.

![Ubuntu Terminal](/assets/images/TerminalUbuntu.png)

Try updating and upgrading all software by :

- Check for any upgradable softwares.
```shell
$ sudo apt update -y
```

- Upgrade all upgradable softwares.
```shell
$ sudo apt upgrade -y
```

Then terminate Ubuntu so the settings can be applied.
```shell
wsl -t Ubuntu-22.04
```
![Terminating Ubuntu](/assets/images/TerminatingRunningWSL.png)

After open WSL2 or Ubuntu again all the settings are applied and Ubuntu is ready to be used.

![Testing Ubuntu 1](/assets/images/TestUbuntu1.png)
![Testing Ubuntu 2](/assets/images/TestUbuntu2.png)
![Testing Ubuntu 3](/assets/images/TestUbuntu3.png)

### Installing Linux on VMware Workstation 16 Player Virtual Machine.

## Installing VMware Workstation 16 Player.

Start by Downloading VMware Workstation 16 Player from https://www.vmware.com/products/workstation-player.html.
