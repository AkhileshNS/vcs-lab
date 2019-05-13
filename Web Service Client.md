# Program 1: Implementing a simple Web Service in Eclipse JEE.

## Prerequisites

Make sure that you have Eclipse installed via the official website (https://www.eclipse.org/downloads/download.php?file=/oomph/epp/2019-03/R/eclipse-inst-win64.exe)

Note: Setup Tomcat server before proceeding to further steps. for reference, please use this tutorial: (https://help.eclipse.org/neon/index.jsp?topic=%2Forg.eclipse.stardust.docs.wst%2Fhtml%2Fwst-integration%2Fconfiguration.html)

## Steps

- Open Eclipse J2E and create new ‘Dynamic Web Project’.

- Create new Class and write a method to be implemented in web service.

- Now go to File-> New->Web Services and c Web service.

- Browse service implementation and select the java class that you have created just now.

- Set client type as ‘Test Client’ and check ‘Monitor web service’ option.

- Finish this wizard box and click run icon.

- Output will display list of methods on one panel and its output in another.

- Select any one method (method which you have created in java class) and give appropriate input.

- Results will be displayed in the bottom tab.

- You can try other built-in web services such as getEndpoint().