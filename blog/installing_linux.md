[<< Main Page](https://supakornpholsiri.github.io/)

# Installing Linux

In this blog I will write about the installation of 3 of linux operating systems : Ubuntu, Debian & MX Linux, via WSL2 and VMware Workstation 16 Player.

## Installing Ubuntu 22.04 LTS with WSL2.
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

## Installing Linux on VMware Workstation 16 Player Virtual Machine.

### Installing VMware Workstation 16 Player.

Start by Downloading VMware Workstation 16 Player from https://www.vmware.com/products/workstation-player.html.

![Download page](/assets/images/VMwareDownload.png)

After opening the installer, when this window pop up, restart your computer to let Windows finish the neccessary updates.

![Restart prompt](/assets/images/RestartPrompt.png)

Open the installer again.

![VMwareInstaller](/assets/images/VMwareInstaller.png)

Accept the terms in License Agreement.

![VMware License Agreement](/assets/images/VMwareLicenseAgreement.png)

Tick Install Windows Hypervisor Platform (WHP) automatically.

![Install WHP](/assets/images/InstallWHP.png)

Tick both options.

![Custom Setup](/assets/images/CustomSetup.png)

Tick both options.

![User Experience Settings](/assets/images/VMwareUserExperienceSetting.png)

Tick where you want VMware Workstation 16 Player's shortcut to be in.

![VMware Shortcut](/assets/images/VMwareShortcut.png)

Begin the installation.

![Install VMware](/assets/images/InstallVMware.png)

Click Finish.

![Finish Installing](/assets/images/FinishSetup.png)

Restart your computer to let VMware Workstation 16 Player finish setting up its configuration.

![Restart Prompt](/assets/images/RestartPrompt2.png)

Open VMware Workstation 16 Player. You can use VMware Workstation 16 Player for free for non-commercial use.

![Version Select](/assets/images/VersionSelect.png)
![Finally done with setting up VMware](/assets/images/FinishVMware.png)

Now VMware Workstation 16 Player is ready to be used.

![VMware](/assets/images/VMware.png)

### Installing Debian 11.4 on VMware Workstation 16 Player Virtual Machine.

Start by downloading Debian 11.4 iso image from https://www.debian.org/distrib

![Debian's Website](/assets/images/DebianWebsite.png)

This blog will only cover how to install Debian via the Internet using Small CDs or USB sticks option.\
https://www.debian.org/distrib/netinst \
For x64 download amd64.\
For x32 download i386.\

![Installing Debian via the Internet](/assets/images/DebianNetlist.png)

Open VMware Workstation 16 Player. Create a new virtual machine.

![VMware](/assets/images/VMware.png)

Install the guest OS with the downloaded iso file.

![Installing guest OS](/assets/images/Installiso.png)

Name your virtual machine and select its location.

![Name VM and set its location](/assets/images/NameAndLoc.png)

Specify disk capacity for your virtual machine. Choose split virtual disk into multiple files for easier time moving the virtual machine to another computer.

![Specify virtual disk size](/assets/images/VirtualDisk.png)

Click Customize Hardware.

![Ready to create](/assets/images/Ready.png)

Adjust the virtual machine's memory to your liking.

![Adjusting memory](/assets/images/Memory.png)

Open the virtual machine. Choose Graphical install.

![Debian BIOS](/assets/images/DebianBIOS.png)

Select a language.

![Select a language](/assets/images/LangSelectDebian.png)