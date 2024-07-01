# Stpe by Step Guide for Amber is a suite installation(biomolecular simulation programs) 
### Amber is distributed in two parts: AmberTools22 and Amber23. Both these software are Dockerized and put into a container which you can use with the help of this manual.
## Note: First, we install WSL2. Secondly, we install the Amber suite.
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


# Please remember the following Steps: "Second, run the Amber Suite Container." 

## Step 1 - Install WinSCP to transfer files to a Linux container from the Windows 10 host
**Note:** Put the username and password with their IP address of Ubuntu installed on wsl2.

![image](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/baffe477-b5e7-412d-8776-39004983924e)


![image](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/3470f020-ba1f-4300-9f79-26ceb3f007f0)



## Step 2 - docker installation on Windows Subsystem for Linux
```bash
	sudo apt update
	sudo apt install docker.io
```

## Step 3 - docker images so load Amber22 docker image
```bash
	sudo docker images
	sudo docker load < /home/hammad/amber22_hammad_vnkn01.tar.gz
```

![image](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/ff7a489e-14d6-49cf-a255-e1323a780612)


**Note:** After loading images  we have the image amber22_hammad_vnkn01

![image](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/c23eb973-2be2-4e90-982b-94bf598f2279)

## Step 4 - Run container with image id.
```bash
docker run -it d943cd2be591
```
![image](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/0a1dcbaa-deba-4f09-92a3-9cbe5bb0a0a2)

## Step 5 - successfully bio tleap run

Test amber is running type   ``` tleap ```

![image](https://github.com/hammadattari/VNKN01-BioInfoLabSoft/assets/44769452/8f2268a2-2471-4073-b261-661890eb65a7)



## Step 6 - Crtl+c to exit the container and start the exited container

```bash
 docker ps -a 
 docker container  start -i a743fc47f9bb
```
