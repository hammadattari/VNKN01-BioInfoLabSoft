This guide outlines the steps to set up a Linux environment using Windows Subsystem for Linux (WSL). WSL allows you to run Linux distributions directly on your Windows machine.

**Prerequisites:**

* A Windows 10 (version 1903 or later) or Windows 11 machine
* Administrator privileges



## Step 1: Enable Windows Subsystem for Linux (WSL)

Open a PowerShell window as Administrator and run the following command:

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

## Step 2 - Enable Virtual Machine feature

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
**Note:** Restart your computer after running this command.

## Step 3 - Install Ubuntu and make a user like Hammad
```powershell
Use 'wsl.exe --list --online' to list available distributions

wsl.exe --install Ubuntu-24.04

```

![wsl](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/5cd9eb36-2f6d-4725-a035-a389c9ec3e0f)

## Step 4 - Install and Enable SSH

```bash
apt install
nano /etc/ssh/sshd_config
sudo systemctl restart ssh or sudo service sshd restart
```

![ssh](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/7ee2b2ed-be2c-4e71-89c4-a25c137f1cf5)

## Step 5 - Change root password and ssh localhost (Optional)

```bash
sudo passwd root
ssh localhost
```
![chroopwd](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/27d7b6f4-501d-48dd-97d3-9a75955b3fad)


