# ⏱️ STOPWATCH React App

A simple and responsive Stopwatch/Timer web application built using **React.js**.

This project is used as a practical **DevOps project** to understand application development, containerization, CI/CD, and AWS deployment.

## 🚀 Features

* Session Timer
* Break Timer
* Start / Pause Timer
* Reset Timer
* Increase / Decrease Session Time
* Increase / Decrease Break Time
* Audio notification when timer completes
* Responsive UI

## 🛠️ Technologies Used

### Frontend

* React.js
* JavaScript
* HTML5
* CSS3
* SCSS

### DevOps

* Git & GitHub
* Jenkins
* Docker
* Nginx

### AWS

* IAM
* EC2
* VPC
* S3
* ECR
* ECS
* Fargate

---

## 💻 Run Locally

```bash
git clone https://github.com/kakijassica/STOPWATCH-ReactApp.git
cd STOPWATCH-ReactApp
npm install
npm start
```

Application:

```text
http://localhost:3000
```

## 🏗️ Production Build

```bash
npm run build
```

Production files are generated inside:

```text
build/
```

---

## 🔄 DevOps Deployment Workflow

```text
GitHub
   ↓
Jenkins
   ↓
React Build
   ↓
Docker Image
   ↓
Amazon ECR
   ↓
Amazon ECS / Fargate
   ↓
Running Container
   ↓
Live Application
```

## ⚙️ Jenkins CI/CD

Jenkins is used to automate the application build and deployment process.

### Pipeline Flow

```text
GitHub
   ↓
Git Checkout
   ↓
npm ci
   ↓
npm run build
   ↓
Docker Build
   ↓
Docker Image
   ↓
ECR
```

---

## 🐳 Docker

The React application is containerized using Docker.

Docker is used to package the application into a portable container image.

### Docker Flow

```text
React Application
      ↓
npm run build
      ↓
Docker Build
      ↓
Docker Image
      ↓
Docker Container
```

---

## ☁️ AWS Deployment

### Amazon VPC

Created a custom AWS VPC for the project with:

* VPC
* Public Subnet
* Private Subnet
* Internet Gateway
* Route Tables
* Security Group
* NAT Gateway
* NACL
* VPC Endpoint

### Amazon ECR

The Docker image is stored in **Amazon Elastic Container Registry (ECR)**.

```text
Docker Image
     ↓
Amazon ECR
```

### Amazon ECS / Fargate

The Docker image from ECR is deployed using **Amazon ECS with Fargate**.

```text
ECR
 ↓
ECS Task Definition
 ↓
ECS Service
 ↓
Fargate
 ↓
Running Container
```

---

## 📌 Project Objective

The main objective of this project is to understand a practical **DevOps deployment workflow** from source code to a running application.

### Concepts Covered

* React application development
* Git & GitHub
* Jenkins CI/CD
* Docker containerization
* AWS IAM
* AWS EC2
* AWS VPC
* AWS S3
* Amazon ECR
* Amazon ECS
* AWS Fargate
* Nginx
* Automated deployment

---

## 👩‍💻 Author

**Jassica K**

GitHub:
https://github.com/kakijassica
