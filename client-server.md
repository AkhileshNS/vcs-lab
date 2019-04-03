# Program 3: Setup a client-server program

To do this we will use python and execute two porgrams on two different powershell windows to sort of simulate a dummy client and server while both use the loopback address as each other's addresses. Note this will only work on Windows 8 and above, below that will require Linux

## Preconfiguration

Make sure you have NodeJS installed before continuing. If you don't, then the easiest way to install is through the chocolatey package manager.

### Chocolatey Setup

open either powershell or cmd prompt **in admininstrator mode** and run the following commands one after another:

for powershell:
````
Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
````

for cmd prompt:
````
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
````

### Python Setup

After you've installed chocolatey, run the following command in your command prompt/powershell in administrator mode to install Python:

````
choco install python -y
````

Then run the following commands to ensure everything was installed properly:
````
python --version
````

If you see no errors, then everything is setup and you can move on to the next step

## Procedure

Now navigate to folder in which you want to setup the project, press shift and right click, click on "open cmd prompt/powershell window here" and enter the following commands:

````
mkdir client-server
cd client-server
````

Open the project folder with your favourite editor and add the following two files:

client.py
````python
import socket
UDP_IP_ADDRESS = "127.0.0.1"
UDP_PORT_NO = 6789
Message = "Hello, Server"
clientSock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
clientSock.sendto(Message, (UDP_IP_ADDRESS, UDP_PORT_NO))
````

server.py
````python
# Again we import the necessary socket python module
import socket
# Here we define the UDP IP address as well as the port number that we have
# already defined in the client python script.
UDP_IP_ADDRESS = "127.0.0.1"
UDP_PORT_NO = 6789
# declare our serverSocket upon which
# we will be listening for UDP messages
serverSock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
# One difference is that we will have to bind our declared IP address
# and port number to our newly declared serverSock
serverSock.bind((UDP_IP_ADDRESS, UDP_PORT_NO))
while True:
    data, addr = serverSock.recvfrom(1024)
    print "Message: ", data
````

Now open two powershell windows in the project folders and enter the following commands:

for the first window:
````
python server.py
````

for the second window:
````
python client.py
````
