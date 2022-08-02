[<< Main Page](https://supakornpholsiri.github.io/)

# Installing Linux

In this blog I will write about the installation of 3 of linux operating systems : Ubuntu, Debian & MX Linux, via WSL2 and VMware Workstation 16 Player.

[Installing Ubuntu 22.04 LTS with WSL2](## Installing Ubuntu 22.04 LTS with WSL2.)

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

Start by Downloading VMware Workstation 16 Player from [https://www.vmware.com/products/workstation-player.html](https://www.vmware.com/products/workstation-player.html).

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

![Version Select](/assets/images/VersionSelect.png) \
![Finally done with setting up VMware](/assets/images/FinishVMware.png)

Now VMware Workstation 16 Player is ready to be used.

![VMware](/assets/images/VMware.png)

### Installing Debian 11.4 on VMware Workstation 16 Player Virtual Machine.

Start by downloading Debian 11.4 iso image from [https://www.debian.org/distrib](https://www.debian.org/distrib)

![Debian's Website](/assets/images/DebianWebsite.png)

This blog will only cover how to install Debian via the Internet using Small CDs or USB sticks option.\
[https://www.debian.org/distrib/netinst](https://www.debian.org/distrib/netinst) \
For x64 download amd64.\
For x32 download i386.

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

Select your location.

![Select your location](/assets/images/LocSelectDebian1.png) \
![Select your location](/assets/images/LocSelectDebian2.png) \
![Select your location](/assets/images/LocSelectDebian3.png)

If there is no locale defined for the language and location you selected you will have to choose your locale.

![Select your locale](/assets/images/LocaleSelectDebian.png)

Configure you keymap.

![Select your keymap](/assets/images/KeymapSelectDebian.png)

Enter the hostname for the system.

![Hostname](/assets/images/HostnameDebian.png)

Enter your domain name. Home users can leave this blank.

![Domain Name](/assets/images/DomainNameDebian.png)

Set up password for root account.

![Root's Password](/assets/images/RootPasswordDebian.png)

Enter your full name.

![User's full name](/assets/images/FullNameDebian.png)

Enter your username for your account.

![Username](/assets/images/UsernameDebian.png)

Set up password for your account.

![Your Password](/assets/images/YourPasswordDebian.png)

For inexperienced users, choose Guided - use entire disk.

![Partition Disk](/assets/images/PartitionDiskDebian.png)

Select your virtual disk to be partitioned.

![Partitioned Disk](/assets/images/PartitionedDiskDebian.png)

For inexperienced users, choose All files in one partition.

![Partitioning Scheme](/assets/images/PartitioningSchemeDebian.png)

Finish Partitioning and write changes to disk.

![Partition Summary](/assets/images/PartitionSummaryDebian.png)

Click Yes.

![Confirm Partitioning](/assets/images/PartitionConfirmDebian.png)

If you want the installer to scan additional DVD installation media to install some additional packages on your system click Yes. Otherwise click No.

![Scan extra installation media](/assets/images/ScanMediaDebian.png)

Select a Debian archive mirror country that is close to your network for faster download time.

![Debian archive mirror country](/assets/images/DebianArchiveMirrorCountry.png)

Select a Debian archive mirror. Usually, deb.debian.org is a good choice.

![Debian archive mirror](/assets/images/DebianArchiveMirror.png)

If you use need to use a HTTP proxy to access the outside world, enter the proxy information. Otherwise leave this field blank.

![Proxy information](/assets/images/ProxyInfoDebian.png)

Choose if you want to participate in the package usage survey.

![Package usage survey](/assets/images/PackageUsageSurveyDebian.png)

Choose additional softwares that you want to install. You can leave it as the installer suggested.

![Additional software](/assets/images/AdditionalSoftwareDebian.png)

Install the GRUB bootloader on the primary virtual drive.

![Grub bootloader](/assets/images/GRUBDebian.png)

Select the primary virtual drive.

![Select the primary virtual drive](/assets/images/VirtualDriveDebian.png)

Finish the installation.

![Finish the installation of Debian.](/assets/images/FinishDebian.png)

Now your Debian is ready to be used.

![Debian](/assets/images/Debian.png)