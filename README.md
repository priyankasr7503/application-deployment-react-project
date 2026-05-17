# Application Deployment React Project

This project demonstrates a complete CI/CD pipeline for deploying a React application using Docker, Jenkins, Docker Hub, and AWS EC2.

---

## 🚀 Project Overview

The application is containerized using Docker, automated with Jenkins, stored in Docker Hub, and deployed on an AWS EC2 instance.

---

## 🛠️ Tech Stack

- React.js
- Docker
- Jenkins
- Docker Hub
- AWS EC2
- Bash Scripting

---

## 📂 GitHub Repository

https://github.com/priyankasr7503/application-deployment-react-project

---

## 🌐 Deployed Application URL

http://15.134.213.245:3000

---

## 🐳 Docker Hub Images

### Development Image
`priyarchandra/applicationdev:latest`

### Production Image
`priyarchandra/applicationprod:latest`

---

## ⚙️ Jenkins Pipeline Stages

1. Clone source code from GitHub
2. Install dependencies
3. Build React application
4. Build Docker image
5. Push Docker image to Docker Hub
6. Deploy application to AWS EC2

---

## ☁️ AWS EC2 Configuration

- Instance Type: t2.micro
- Operating System: Ubuntu
- Security Group Rules:
  - Port 22 (SSH)
  - Port 3000 (Application)
  - Port 8080 (Jenkins)
  - Port 50000 (Jenkins Agent)

---

## 📈 Monitoring Script

A shell script (`health-check.sh`) is used to monitor application health.

```bash
#!/bin/bash

URL="http://15.134.213.245:3000"
STATUS=$(curl -o /dev/null -s -w "%{http_code}" $URL)

if [ "$STATUS" -eq 200 ]; then
    echo "Application is UP"
else
    echo "Application is DOWN - HTTP Status: $STATUS"
fi
