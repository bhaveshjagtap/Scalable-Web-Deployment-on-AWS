# Scalable Web Deployment on AWS ☁️🚀

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![PM2](https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white)

A robust and highly available web application deployment architecture utilizing Node.js, hosted on Amazon Web Services (AWS) EC2. This repository demonstrates core Cloud and DevOps principles, showcasing how to reliably deploy and manage a web application (featuring a responsive 2048 game as the payload) using PM2 for production-grade process management.

This project is designed to highlight proficiency in cloud infrastructure management, server administration, and application deployment strategies.

## ✨ Architecture & Features

* **High Availability:** Application processes are managed by PM2, ensuring automatic restarts in the event of failure or server reboots.
* **Cloud Infrastructure:** Hosted on AWS EC2 compute instances, providing a foundation for horizontal and vertical scaling.
* **Production-Ready Process Management:** Utilizes PM2 daemon for zero-downtime reloads and comprehensive application monitoring.
* **Version Control & Deployment:** Source code is maintained and deployed via Git/GitHub.

## 🛠️ Prerequisites

To provision this architecture or set up your own instance, you will need:
* An active AWS Account with an EC2 instance provisioned (Ubuntu/Amazon Linux recommended).
* Node.js and npm installed on the server.
* Git installed on the server.
* PM2 installed globally (`npm install -g pm2`).

## 🚀 Deployment Instructions

**1. Access the EC2 Instance via SSH**
```bash
ssh -i /path/to/your-key.pem ec2-user@your-ec2-public-ip
```

**2. Clone the Repository**
```bash
git clone https://github.com/bhaveshjagtap/scalable-web-deployment-aws.git
cd scalable-web-deployment-aws
```

**3. Install Application Dependencies**
```bash
npm install
```

**4. Initialize the Application with PM2**
Start the Node.js server to run as a background daemon.
```bash
pm2 start server.js --name "web-app-node"
```
*(Note: Replace `server.js` with your actual entry point file if different).*

## ⚙️ Persistence & Automation (PM2)

To ensure the application daemon automatically restarts if the AWS EC2 instance is rebooted:

1. Generate the system startup script:
```bash
pm2 startup
```
2. Execute the command outputted by the previous step.
3. Save the current PM2 process list to persist across reboots:
```bash
pm2 save
```

## 🌐 Network Configuration & Access

Ensure your AWS EC2 Security Group is configured to allow inbound TCP traffic on the specific port your Node.js application utilizes (e.g., Port 80 for HTTP, or custom ports like 3000).

Access the deployed application via your EC2 instance's Public IPv4 address or associated DNS name:
```text
http://<your-ec2-public-ip>:<port>
```

## 🤝 Contributing

Contributions, architectural suggestions, and feature requests are welcome!
