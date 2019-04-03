# Program 4: Create a web server using NodeJS

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

### NodeJS Setup

After you've installed chocolatey, run the following command in your command prompt/powershell in administrator mode to install NodeJS:

````
choco install nodejs -y
````

Then run the following commands to ensure everything was installed properly:
````
node --version

npm --version
````

If you see no errors, then everything is setup and you can move on to the next step

## Procedure

Navigate to any folder where you would like to create your webserver. Then press shift and right-click, click on open cmd prompt/powershell window here. Then execute the following two commands:

````
mkdir (YOUR PROJECT NAME)

cd (YOUR PROJECT NAME)

npm init
````

After entering npm init, keep pressing enter and until you get back to the command prompt/powershell window, then execute the following command:

````
npm i express nodemon
````

After you have successfully installed these packages, open the project with your favourite code editor and open the package.json file and make the following changes to the "scripts" section:
````json
"scripts": {
  "test": "echo \"Error: no test specified\" && exit 1",
  "start": "nodemon index.js" // <- Add This
}
````

Then create a file called index.js in your project directory and enter in the following code in the file

````javascript
const express = require('express'),
app = express(),
port = process.env.PORT || 3000;

app.get('/', (req, res) => {
    res.send("Hello There")
});

app.listen(port, () => {
    console.log(`Example app listening on port ${port}!`);
});
````

Finally on cmd prompt/powershell make sure you are in your project directory and execute the following command:

````
npm start
````

Then open your browser and enter the url "localhost:3000"
