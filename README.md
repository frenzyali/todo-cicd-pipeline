<h1 align="center">🧩 ToDo CI/CD Pipeline</h1>

<p align="center">
  <img src="https://img.shields.io/badge/CI/CD-Jenkins-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Docker-Containerized-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/AWS-Deployed-success?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Node.js-App-green?style=for-the-badge"/>
</p>

<p align="center">
  A fully automated <b>CI/CD Pipeline</b> for a Node.js ToDo Application using <b>Jenkins, Docker, and AWS EC2</b>.
</p>

---

## 🚀 Project Overview

This project demonstrates a **two-tier CI/CD pipeline** setup for a simple ToDo web app.  
The pipeline automates the entire process — from **Git commit → Jenkins Build → Docker Image → Deployment** — all hosted on an AWS EC2 instance.

---

## 🧠 Tech Stack

| Layer | Tool / Technology |
|-------|-------------------|
| Frontend | HTML, CSS, EJS (Node.js Templates) |
| Backend | Node.js, Express.js |
| Containerization | Docker, Docker Compose |
| CI/CD | Jenkins |
| Deployment | AWS EC2 |
| Version Control | Git & GitHub |

---

## 🏗️ Pipeline Flow

```text
GitHub Push  ➜  Jenkins Build Trigger (via Webhook)
              ➜  Docker Build & Push (Local/ECR)
              ➜  Container Deployment (via Docker Compose)
              ➜  Running ToDo App on AWS EC2


⚙️ Setup & Installation
🐧 On Local Machine / EC2

Clone the repo

git clone https://github.com/frenzyali/todo-cicd-pipeline.git
cd todo-cicd-pipeline


Run the containers

docker-compose up -d


Access the app

http://<your-ec2-public-ip>:8000
