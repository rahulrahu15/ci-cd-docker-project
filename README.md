# 🐳 CI/CD Docker Project — Multi-Stage + Distroless + GitHub Actions

A production-ready DevOps project featuring a **two-tier web application (Flask backend + static HTML frontend)** containerized with Docker and deployed on AWS EC2. The project includes a **CI/CD pipeline using GitHub Actions** and optimized Docker images using **multi-stage builds and distroless base images** for improved security and performance.

---

## 🚀 Project Architecture

- **Frontend** → Static HTML served from Nginx (Docker)
- **Backend** → Python Flask API (Docker)
- **Docker Multi-Stage Builds** to minimize image size
- **Distroless Runtime Images** for production-grade security
- **GitHub Actions CI Pipeline** to build and push images on each commit
- **Manual Deployment on AWS EC2 using Docker**

---

## 🎯 Features

- 🧱 Backend & Frontend running in separate Docker containers  
- 🐳 Multi-stage Docker builds  
- 🔐 Distroless images (minimal, secure runtime)  
- ⚙️ Automated CI pipeline using GitHub Actions  
- 🚀 Deployable on any Linux server / EC2 instance  
- 📦 Lightweight & optimized image sizes  

---

## 🏗️ Technology Stack

- Docker & Docker Hub  
- Flask (Python Backend)  
- Nginx (Frontend)  
- GitHub Actions (CI Pipeline)  
- AWS EC2 (Deployment)  
- Linux / Ubuntu  

---

## 📂 Project Structure

ci-cd-docker-project/
│
├── backend/
│ ├── app.py
│ ├── requirements.txt
│ └── Dockerfile
│
├── frontend/
│ ├── index.html
│ └── Dockerfile
│
└── .github/workflows/ci.yml


---

## 🔧 CI/CD Pipeline Workflow

The pipeline runs automatically when code is pushed to `main`:

1️⃣ Checkout repository  
2️⃣ Build backend & frontend Docker images  
3️⃣ Tag images with commit SHA  
4️⃣ Push images to Docker Hub  

This simulates a **real-world DevOps CI workflow**.

---

## 🐳 Build & Run Containers Manually

### Backend
```bash
docker build -t backend-app ./backend
docker run -d -p 5000:5000 backend-app
