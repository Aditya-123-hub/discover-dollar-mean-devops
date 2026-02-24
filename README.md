# MEAN DevOps Assignment

This project demonstrates a complete DevOps workflow for deploying a full-stack **MEAN (MongoDB, Express, Angular, Node.js)** application using:

- Docker
- Docker Compose
- Docker Hub
- GitHub Actions (CI/CD)
- AWS EC2 (Ubuntu)
- Nginx Reverse Proxy


## 📌 Project Objective

Containerize, orchestrate, and deploy a MEAN stack application with:

✔ Dockerized frontend & backend  
✔ MongoDB setup  
✔ Docker Compose orchestration  
✔ CI/CD pipeline  
✔ Cloud deployment on AWS  
✔ Nginx reverse proxy  
✔ Application accessible via Port 80  


## Tech Stack

| Layer | Technology |
|------|------------|
| Frontend | Angular |
| Backend | Node.js + Express |
| Database | MongoDB |
| Containerization | Docker |
| Orchestration | Docker Compose |
| CI/CD | GitHub Actions |
| Registry | Docker Hub |
| Cloud | AWS EC2 (Ubuntu) |
| Reverse Proxy | Nginx |


## Dockerization

### Backend
- Base Image: Node 18
- Port: 8080

### Frontend
- Multi-stage Docker build
- Angular production build
- Served via Nginx
- Port: 80

## Docker Images

Images pushed to Docker Hub:

- `kubeaditya957/mean-backend`
- `kubeaditya957/mean-frontend`


## Docker Compose Setup

Services:

- MongoDB
- Backend
- Frontend
- Nginx (Reverse Proxy)


## MongoDB Configuration Fix

Original Issue:

Backend attempted connection to:
mongodb://localhost:27017/dd_db

Problem:
Inside Docker, `localhost` refers to the container itself.

Solution:
Updated DB config:
mongodb://mongo:27017/dd_db


✔ Enabled container-to-container communication.


## CI/CD Pipeline (GitHub Actions)

Pipeline triggers on:

✔ Push to `main` branch

Steps:

1️⃣ Checkout code  
2️⃣ Docker Hub login (using Access Token)  
3️⃣ Build backend image  
4️⃣ Push backend image  
5️⃣ Build frontend image  
6️⃣ Push frontend image  

✔ Secrets stored securely via GitHub Repository Secrets.


## 🔐 Secure Credentials

Used:

- Docker Hub Access Token
- GitHub Secrets:
  - `DOCKER_USERNAME`
  - `DOCKER_PASSWORD`

✔ No plaintext credentials.


## AWS Deployment

Environment:

- AWS EC2
- Ubuntu Server 22.04
- Docker & Docker Compose installed

Deployment Steps:

✔ SSH into EC2  
✔ Pull Docker images  
✔ Create docker-compose.yml  
✔ Run containers  


## Nginx Reverse Proxy

Configured routing:

- `/` → Frontend
- `/api` → Backend

Enabled:

✔ Single entrypoint (Port 80)  
✔ Clean production-style architecture  


## Application Verification

✔ Frontend UI running  
✔ Backend API responding  
✔ MongoDB connected  

Tested Endpoints:

- `http://<EC2_PUBLIC_IP>`
- `http://<EC2_PUBLIC_IP>/api`


## 📸 Screenshots Included

✔ CI/CD Pipeline Execution  
✔ Docker Image Build & Push  
✔ Running Containers  
✔ AWS Deployment  
✔ Nginx Reverse Proxy  


## Key Learnings

- Docker multi-stage builds
- Container networking
- MongoDB hostname resolution
- CI/CD automation
- Secure secrets management
- AWS cloud deployment
- Reverse proxy configuration



