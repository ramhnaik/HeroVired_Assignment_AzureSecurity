This file provides step-by-step guide to deploy a MEAN (MongoDB, Express.js, Angular, Node.js) application on Azure and set up a monitoring dashboard.

### Step 1: Deploy the MEAN Application on Azure
##### a.Create an Azure Account: If you don't have an Azure account, you can create one here.
##### b.Set Up an Azure Virtual Machine:
Go to the Azure portal and create a new Virtual Machine (VM) with Ubuntu as the operating system.
Configure the VM settings (size, region, etc.) and create the VM.

#### c.Install MEAN Stack on the VM:
SSH into your VM.
Update the package list and install Node.js:
~~~
sudo apt update
sudo apt install nodejs npm
~~~
Install MongoDB:
~~~
sudo apt install -y mongodb
sudo systemctl start mongodb
sudo systemctl enable mongodb
~~~
Install Angular CLI:
~~~
sudo npm install -g @angular/cli
~~~
Install Express.js:
~~~
sudo npm install express --save
~~~

#### d.Deploy Your Application:

Clone your application repository from GitHub:
git clone https://github.com/UnpredictablePrashant/ResumeAI.git
cd ResumeAI
Install the application dependencies:
npm install
Start your application:
npm start

### Step 2: Set Up Monitoring Dashboard
#### a.Azure Monitor:

Go to the Azure portal and navigate to Azure Monitor.
Create a new dashboard and add metrics for your VM, such as CPU usage, memory usage, and network traffic.

#### b.Application Insights:

Enable Application Insights for your application to monitor performance and usage.
Add the Application Insights SDK to your Node.js application:
~~~
npm install applicationinsights --save
~~~

Initialize Application Insights in your application code:
~~~
const appInsights = require('applicationinsights');
appInsights.setup('<YOUR_INSTRUMENTATION_KEY>').start();
~~~

#### c.Custom Dashboards:

Create custom dashboards in Azure Monitor to visualize logs, performance metrics, and alerts.
Use tools like Grafana or OpenObserve for more advanced monitoring and visualization


### Step 3: Verify the Deployment
Access the frontend URL:
~~~
https://<ResumeAIFrontend>.azurewebsites.net
~~~
Access the backend URL:
~~~
https://<ResumeAIBackend>.azurewebsites.net
~~~
Test the application functionality.
Check the Application Insights logs for any errors.
