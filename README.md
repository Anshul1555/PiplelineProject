# CI/CD Pipeline with GitHub Actions – Full Stack App

## 📋 Overview

This project demonstrates how to implement a **Continuous Integration (CI)** and **Continuous Deployment (CD)** pipeline for a full-stack application using **GitHub Actions** and **Render**.

The goal is to ensure clean, testable code is merged into `develop` and only successfully tested and approved changes get deployed to `main`.

---

## 🚀 Features

- ✅ **CI Pipeline**: Automatically runs tests on all pull requests targeting the `develop` or `staging` branches.
- ✅ **CD Pipeline**: Automatically builds and tests code pushed to the `main` branch and waits for manual approval before deploying to Render.
- ✅ **Manual Approval Step**: Protects production deployment by requiring human confirmation before deploying.
- ✅ **Environment-Based Deployment**: Uses GitHub’s `environments` for safe and reviewed deployments.

---

## 🔀 Branching Strategy

- `main`: production-ready code, auto-deployed after approval
- `develop`: integration branch for ongoing development
- `feature/*`: individual feature branches created from `develop`

---

## ⚙️ GitHub Actions Workflows

### 🔧 `Test Workflow` (CI)

**File**: `.github/workflows/test.yml`

**Triggered On**:

- Pull requests to `develop` or `staging`

**Steps**:

- Checkout code
- Set up Node.js
- Install dependencies
- Run build
- Run Cypress component tests

---

### 🚀 `Deploy Workflow` (CD)

**File**: `.github/workflows/deploy.yml`

**Triggered On**:

- Push to `main` branch

**Steps**:

- Checkout code
- Set up Node.js
- Install dependencies
- Run build
- Run tests
- **Wait for manual approval** (via GitHub Environments)
- Deploy to Render using a secure Deploy Hook URL

---

## 🛠️ Technologies Used

- **GitHub Actions**
- **Node.js 21.x**
- **Cypress / Component Testing**
- **Render (for deployment)**
- **Git Flow branching model**

---

## 🔒 GitHub Secrets

- `RENDER_DEPLOY_URL`: Stores your Render Deploy Hook securely for automated deployment.

---

## 📦 Project Setup

```bash
# Install dependencies
npm install

# Run local tests
npm run test-component
```

## 🌐 Live Deployment

The live app is deployed on **Render** and is automatically updated when code is pushed to the `main` branch and manually approved.

👉 **Live Site Link**:
QA/ Develop : https://piplelineproject-develop.onrender.com
Production/ Main: https://piplelineproject.onrender.com

---

## 👤 Author

**Anshul Sharma**  
Full-Stack Developer | QA Engineer | Bootcamp Graduate  
🔗 [GitHub Profile](https://github.com/Anshul1555)

---

## 📝 License

This project is part of the **University of Toronto Full Stack Coding Bootcamp – Challenge 19: CI/CD with GitHub Actions**.
