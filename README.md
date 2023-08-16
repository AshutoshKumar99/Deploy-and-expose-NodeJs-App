# Deploying a Node.js Application on AWS EC2

This README guide provides step-by-step instructions for deploying a Node.js application on an AWS EC2 instance. It covers both testing the project locally and deploying it on AWS.

## Testing the Project Locally

1. **Clone the Project:**
   ```bash
   git clone https://github.com/AshutoshKumar99/Deploy-and-expose-NodeJs-App.git
   ```

2. **Set Up Environment Variables:**
   Create a `.env` file in the project directory and set the following environment variables:
   ```dotenv
   DOMAIN=""
   PORT=3000
   STATIC_DIR="./client"
   ```

3. **Initialize and Start the Project:**
   Navigate to the project directory, install dependencies, and start the application.
   ```bash
   cd Deploy-and-expose-NodeJs-App
   npm install
   npm run start
   ```

## Setting Up an AWS EC2 Instance

1. **Create an IAM User and Log In:**
   - Create an IAM user with the `AmazonEC2FullAccess` permission and password access.
   - Log in to your AWS Console using the IAM user's credentials.

2. **Launch an EC2 Instance:**
   - Choose an Ubuntu OS image.
   - Create a new key pair and download the `.pem` private key file.
   - Select an instance type, such as `t2.micro`.

3. **Connect to the Instance using SSH:**
   Use the downloaded private key (`.pem` file) to connect to the instance via SSH.
   ```bash
   ssh -i instance.pem ubuntu@<IP_ADDRESS>
   ```

## Configuring Ubuntu on Remote VM

1. **Update Packages:**
   Run the following command to update outdated packages and dependencies.
   ```bash
   sudo apt update
   ```

2. **Install Git:**
   Install Git on the remote VM.

3. **Configure Node.js and npm:**
   Set up Node.js and `npm` as needed for your project.

## Deploying the Project on AWS

1. **Clone the Project on Remote VM:**
   Clone the project repository on the remote VM.
   ```bash
   git clone https://github.com/AshutoshKumar99/Deploy-and-expose-NodeJs-App.git
   ```

2. **Set Up Environment Variables:**
   Create a `.env` file in the project directory (if not already done) and set the required environment variables as before.

3. **Initialize and Start the Project:**
   Navigate to the project directory, install dependencies, and start the application.
   ```bash
   cd Deploy-and-expose-NodeJs-App
   npm install
   npm run start
   ```

   **Note:** You might need to edit the inbound rules in the security group of your EC2 instance to allow traffic on the specified port.

Congratulations! Your Node.js application is now deployed and running on AWS EC2. 🎉
