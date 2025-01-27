1. Prepare the Application
   
Clone the repository or set up your own MEAN app locally.
git clone https://github.com/UnpredictablePrashant/ResumeAI
cd ResumeAI
Install dependencies:
npm install
Test the app locally to ensure everything is working:
npm start

2. Set Up Azure Services
a. Create Azure Resources
Azure Cosmos DB for MongoDB:
Go to the Azure Portal.
Create a Cosmos DB instance with a MongoDB API.
Note the connection string for later use.
Azure App Service for the Node.js backend:

Create an Azure App Service for hosting the backend (Express API).
Choose a Linux environment and Node.js runtime.
Azure Static Web Apps for Angular:

Create a Static Web App to host the Angular frontend.
Link it to your GitHub repository to enable CI/CD for the frontend.
Azure Monitor for Application Insights:

Enable Application Insights for both App Service and Static Web Apps.
Use this to collect logs, metrics, and traces.

3. Deploy the MEAN Application
a. Backend (Node.js) Deployment
Zip the backend files (excluding node_modules).

Deploy to the Azure App Service:

az webapp deployment source config-zip \
    --resource-group <resource-group-name> \
    --name <app-service-name> \
    --src <path-to-backend-zip>
Update environment variables:

Go to the App Service -> Configuration.
Add variables for DB_URI, PORT, and others needed.
b. Frontend (Angular) Deployment
Build the Angular app:
ng build --prod
Deploy the dist folder to Azure Static Web Apps.

4. Monitoring Dashboard
Azure Monitor Setup:

Go to the Azure Monitor service.
Create a new workbook.
Add metrics for:
CPU and memory usage for the App Service.
Requests and responses for the API.
Page views and user sessions for Static Web Apps.
Application Insights Integration:

Use the SDK to track custom events and metrics.
Add the following to your Node.js app:
const appInsights = require("applicationinsights");
appInsights.setup("<YOUR_INSTRUMENTATION_KEY>").start();
Cosmos DB Metrics:
View query performance, storage usage, and throughput in the Azure Cosmos DB metrics blade.

5. Verify and Test
Verify the application runs end-to-end.
Test the monitoring dashboard by triggering traffic and viewing the stats.
Would you like code snippets or details about specific steps?
