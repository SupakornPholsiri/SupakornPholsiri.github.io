[<< Main Page](https://supakornpholsiri.github.io/)

# Installing Linux

In this blog I will write about the installation of 3 of linux operating systems : Ubuntu, Debian & MX Linux, via WSL2 and VMware workstation player.

### Installing Ubuntu 22.04 LTS with WSL2.
In order to use WSL2. We have to start by downloading Windows Subsystem for Linux Preview from Microsoft store.

![Windows Subsystem for Linux Preview](/assets/images/WSLPreview.png)

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

Try updating and upgrading all software in the repository by :

```shell
$ sudo apt update -y
```
Check for any upgradable softwares.

```shell
$ sudo apt upgrade -y
```
Upgrade all upgradable softwares.

