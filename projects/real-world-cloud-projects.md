### **Simple Cloud Project: Deploying a Web Application with Continuous Integration and Disaster Recovery**

---

### **Project Overview:**

* **Goal**: Deploy a simple web application (e.g., a Node.js app) on **AWS** and **Azure**, set up CI/CD pipelines for automated deployment, configure disaster recovery, and monitor the application.
* **Services Involved**:

  * **AWS EC2** (Web Server)
  * **Azure App Services** (Web Hosting)
  * **AWS Route 53** (DNS management)
  * **GitHub** (CI/CD pipeline)
  * **AWS CloudWatch & Azure Monitor** (Monitoring)
  * **AWS S3 and Azure Blob Storage** (Backup)

---

### **Step 1: Set up the Web Application**

1. **Create a basic Node.js application:**

   * Initialize a Node.js app using Express.js.
   * Add a basic endpoint, like a "Hello World" page.

   ```bash
   mkdir simple-web-app
   cd simple-web-app
   npm init -y
   npm install express
   ```

   **app.js:**

   ```javascript
   const express = require('express');
   const app = express();

   app.get('/', (req, res) => {
     res.send('Hello, world! Welcome to my simple cloud app.');
   });

   app.listen(3000, () => {
     console.log('Server is running on port 3000');
   });
   ```

2. **Push the code to GitHub**:

   * Create a new GitHub repository and push your code there.

   ```bash
   git init
   git remote add origin <your-repo-url>
   git add .
   git commit -m "Initial commit"
   git push -u origin master
   ```

---

### **Step 2: Set up the Infrastructure**

1. **AWS EC2 Deployment** (Web Server)

   * Log in to your AWS Console and launch a new EC2 instance (Ubuntu or Amazon Linux 2).
   * Install Node.js on your EC2 instance.

   ```bash
   sudo apt update
   sudo apt install nodejs npm
   ```

   * Clone the GitHub repository and start the application.

   ```bash
   git clone <your-repo-url>
   cd simple-web-app
   node app.js
   ```

   * Configure security groups to allow HTTP access on port 80.
   * Access your application using the EC2 public IP.

2. **Azure App Service Deployment** (Web Hosting)

   * Log in to the Azure Portal and create a **Web App**.
   * Select the **Node.js** runtime stack.
   * Configure the app to pull from GitHub for continuous deployment.
   * Ensure that the app is running and accessible via a URL.

---

### **Step 3: Set up Continuous Integration and Continuous Deployment (CI/CD)**

1. **GitHub Actions CI/CD Pipeline**

   * In your GitHub repository, go to **Actions** and set up a new workflow for continuous deployment.
   * Below is a basic **GitHub Actions YAML** file for the Node.js application deployment:

   **.github/workflows/deploy.yml:**

   ```yaml
   name: Deploy to AWS and Azure

   on:
     push:
       branches:
         - main

   jobs:
     deploy:
       runs-on: ubuntu-latest

       steps:
       - name: Checkout code
         uses: actions/checkout@v2

       - name: Set up Node.js
         uses: actions/setup-node@v2
         with:
           node-version: '14'

       - name: Install dependencies
         run: npm install

       - name: Deploy to AWS
         run: |
           ssh -i "path/to/your/aws-key.pem" ubuntu@<ec2-public-ip> << 'EOF'
             cd simple-web-app
             git pull
             npm install
             pm2 restart app.js
           EOF

       - name: Deploy to Azure
         run: |
           az webapp deployment source config --name <your-app-name> --resource-group <your-resource-group> --repo-url <your-repo-url> --branch main --manual-integration
   ```

   * This file deploys the app to both AWS EC2 and Azure App Service when changes are pushed to the **main** branch.

---

### **Step 4: Set up Monitoring and Logging**

1. **AWS CloudWatch Logs**:

   * In AWS, go to **CloudWatch** and create a **Log Group**.
   * Configure your EC2 instance to send logs to CloudWatch.

   ```bash
   sudo apt-get install awslogs
   sudo service awslogs start
   ```

2. **Azure Monitor**:

   * In the Azure Portal, navigate to **Monitor**.
   * Set up **Application Insights** for your App Service to track performance and errors.

---

### **Step 5: Set up Backup and Disaster Recovery**

1. **AWS S3 Backup**:

   * Create an **S3 Bucket** for storage.
   * Use AWS CLI to back up application files to S3.

   ```bash
   aws s3 cp /path/to/application s3://your-backup-bucket/ --recursive
   ```

2. **Azure Blob Storage Backup**:

   * Create a **Blob Storage** container in Azure.
   * Use **AzCopy** or the Azure CLI to copy files.

   ```bash
   az storage blob upload-batch -d <container-name> --source /path/to/application
   ```

---

### **Step 6: Set up Disaster Recovery**

1. **AWS Route 53 Failover Routing**:

   * Set up **Route 53** to manage DNS failover between AWS and Azure instances.

2. **Azure Traffic Manager**:

   * Set up **Azure Traffic Manager** to route traffic between Azure App Service and AWS EC2 for failover.

---

### **Step 7: Final Testing**

* Test the following:

  * Deploy the app using GitHub Actions to AWS and Azure.
  * Verify that the application is running on both platforms.
  * Simulate a failure by stopping the AWS EC2 instance and ensuring the traffic is routed to Azure.
  * Verify that logs are being captured in CloudWatch (AWS) and Azure Monitor.
  * Test backup restoration by deleting files and restoring them from S3/Blob Storage.

---

### **Conclusion**

By completing this project, you'll have:

* Deployed a simple Node.js web application on both **AWS EC2** and **Azure App Services**.
* Set up a **CI/CD pipeline** using **GitHub Actions**.
* Configured **monitoring and logging** with **AWS CloudWatch** and **Azure Monitor**.
* Implemented **disaster recovery** with **AWS Route 53** and **Azure Traffic Manager**.
* Created **backups** using **AWS S3** and **Azure Blob Storage**.
