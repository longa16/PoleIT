# 🚀 Deployment Guide – PoleIT-VAL Website

This document details the **deployment process** of the **PoleIT-VAL** astronomy center website, using modern DevOps tools and best practices.

## 📦 1. Dockerization

### 🐳 Dockerfile
A `Dockerfile` is used to containerize the PHP-based web application (or Node.js if applicable).

    ```bash
    # Build the image
    docker build -t poleit-val .
    
    # Run the container locally
    docker run -p 3000:3000 poleit-val

### 🧱 Docker Compose
We use docker-compose.yml to bundle the app with its dependencies (e.g., database):

     ```bash
    # Start all services
    docker-compose up -d

## ⚙️ 2. CI/CD – GitHub Actions
GitHub Actions automates testing, linting, building, and deployment:
 CI Pipeline Overview
   -Lint code (PHPStan, ESLint, etc.)
   -Security checks with Dependabot
   -Run tests on every PR
   -Build and publish Docker image

## ☸️ 4. Deployment to K3s
We use K3s to run our production cluster (lightweight Kubernetes).
