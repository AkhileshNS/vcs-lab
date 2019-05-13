# Program 6: Web Application using Google App Enginer

## Prerequisites

Make sure you have a GCP Account with a billing method in place as it is required in order to enable deployment of the web application

## Steps

- Enter you GCP Account console, and go to Google App Enginer

- Press the Cloud Shell option on the top right corner - the first option 

- After launching this, in the cloud shell enter the following command:

  ````git
  git clone https://github.com/GoogleCloudPlatform/nodejs-getting-started.git
  ````

- After which, change directory into the folder that you just cloned by executing the command:

  ````bash
  cd nodejs-getting-started/1-hello-world
  ````

- And run the following npm command:

  ````npm
  npm i
  ````

  and then after the packages have been installed, run:

  ````npm
  npm start
  ````

  You can now preview your web app on port 8080 (on the top right corner of the cloud shell, you will find an option called web preview, use the same to open the preview)

- Once this is done, in the cloud console press ctrl + c and enter the following two commands:

  ````bash
  gcloud app create
  
  gcloud app deploy
  ````

  When running the second one, you will be prompted to enable a service by GCP in order to deploy, enable this and go back to the console and run the second command again. Note this service requires a billing account to be setup in order to proceed

- Finally when the app is deployed you can view the app in your browser by entering in the following url:

  https://<YOUR_APP_NAME>.appspot.com