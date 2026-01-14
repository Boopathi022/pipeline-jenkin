🚀 Jenkins CI/CD Project – Automated Docker Deployment on AWS

📌 Project Overview

This project demonstrates an automated CI/CD pipeline using Jenkins to build and deploy a Dockerized application on an AWS EC2 instance.

The Jenkins job is already created and configured.
Any new code push to GitHub automatically triggers the pipeline and deploys the updated application.

> ✅ Focus: Real CI/CD execution, not Jenkins setup





🧠 CI/CD Workflow

    GitHub (Code Push)
            ↓
    Jenkins Job (Pipeline)
            ↓
    Docker Image Build
            ↓
    SSH Deployment to EC2
            ↓
    Application Live on AWS




🛠 Tools Used

Tool	      Purpose

GitHub	    Source code repository
Jenkins	    CI/CD automation
Docker      Build & run application
AWS EC2	    Deployment server
SSH	    Remote  Deployment




📁 Repository Contents

    .
    ├── Dockerfile
    ├── index.html
    ├── Jenkinsfile
    └── README.md



⚙️ Jenkins Job Configuration (Already Done)

✔ Jenkins pipeline job created
✔ GitHub repository connected
✔ Webhook configured for auto-trigger
✔ Jenkinsfile used as pipeline script
✔ Docker installed on Jenkins & EC2
✔ SSH access configured to EC2

> No manual pipeline execution required after setup.





📜 Jenkins Pipeline Stages

1️⃣ Source Code Checkout
Jenkins pulls the latest code from GitHub.

2️⃣ Docker Image Build
A Docker image is built using the Dockerfile.

3️⃣ Deployment to AWS EC2
Stops existing container (if any)
Removes old container
Runs the new container on port 8080


✔ Zero manual intervention.



▶️ Deployment Verification

Open in browser:

    http://<EC2_PUBLIC_IP>:8080

🎉 Application successfully deployed via Jenkins CI/CD pipeline.



🔄 Automatic Deployment

Any commit or push to the GitHub repository
Triggers Jenkins automatically
Builds and deploys the latest version

This ensures continuous integration and continuous deployment.


Description:
Implemented an automated Jenkins CI/CD pipeline that builds Docker images and deploys containerized applications to AWS EC2. The pipeline is triggered automatically by GitHub commits and performs end-to-end deployment using SSH.



🧠 Key Skills Demonstrated

Jenkins Pipeline as Code (Jenkinsfile)
Docker image creation & container management
Automated deployments using CI/CD
GitHub–Jenkins integration
AWS EC2 application hosting
Production-style DevOps workflow



👤 Author

     Mahendra Boopathi R 
     DevOps Engineer (Fresher) | CI/CD | Docker | AWS
