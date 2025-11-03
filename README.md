🚀 To-Do App with CI/CD Pipeline using Jenkins, Docker & AWS EC2
🧩 Project Overview

This project demonstrates a complete CI/CD pipeline for a simple Node.js To-Do application.
The pipeline automates the entire workflow — from code commit to deployment — using Jenkins, Docker, Docker Hub, and AWS EC2.

🏗️ Project Architecture
GitHub Repo  →  Jenkins (EC2)  →  Docker Image Build  →  Docker Hub Push  →  Docker-Compose Deploy (EC2)


Tech Stack:

Frontend / Backend: Node.js

Containerization: Docker

Orchestration: Docker Compose

CI/CD: Jenkins

Hosting: AWS EC2

Version Control: GitHub

⚙️ CI/CD Pipeline Flow

Developer pushes code to GitHub repository

GitHub Webhook triggers Jenkins automatically

Jenkins Pipeline performs:

Clones the repository

Builds Docker image

Pushes image to Docker Hub

Deploys container via Docker Compose on EC2

The app becomes available via EC2 public IP

🧰 Tools & Technologies Used
Tool	Purpose
Jenkins	CI/CD automation
Docker	Containerization of the Node.js app
Docker Hub	Image registry for deployment
AWS EC2	Server to host Jenkins and containers
GitHub Webhooks	Automated build triggers# todo-cicd-pipeline
