# Program 5: Visualize Cloud Network using Cloudsim-plus

To do this we will make use of cloudsim-plus, a new and improved version of cloudsim 3.0

## Preconfiguration

Make sure you have NodeJS installed before continuing. If you don't, then the easiest way to install is through the chocolatey package manager.

### Chocolatey Setup

open either powershell or cmd prompt **in admininstrator mode** and run the following commands one after another:

for powershell:

```
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

for cmd prompt:

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

### Git Setup

After you've installed chocolatey, run the following command in your command prompt/powershell in administrator mode to install Python:

```
choco install git -y
```

Then run the following commands to ensure everything was installed properly:

```
git --version
```

If you see no errors, then everything is setup and you can move on to the next step

## Prerequisites

You will also need Eclipse setup similar to the previous program

## Procedure

Open a powershell window or git bash and enter the following command:

````git
git clone https://github.com/ManoelCampos/cloudsim-plus.git
````

This will clone a repository into the directory from which you ran the command. Now open Eclipse and follow these steps:

Note. if you need a video version of the same. please see (https://youtu.be/oO-a5-cZBps)

- Go to File -> Import and in the options Maven -> Existing Maven Repositories
- Now browse to where you have cloned the repo and choose that folder. Then click finish
- When prompted to install additional software, click next and finish. 
- If you see a prompt that starts with "Warning: You are installing software that contains unsigned content", don't be alarmed, simply choose 'install anyway'. (Note. You'll be prompted to restart eclipse, go ahead and do so)
- When this is done, go to cloudsim-plus-example -> src/main/java -> org.cloudsimplus.examples -> BasicFirstExample.java and click run