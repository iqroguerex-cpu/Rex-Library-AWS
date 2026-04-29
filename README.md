# ⚙️ REX Intelligence API — Serverless Multi-Tenant Backend

<p align="center">

[![Live Demo](https://img.shields.io/badge/Live%20Demo-REX.LIBRARY-00C853?style=for-the-badge)](https://main.d2f692z9x36m90.amplifyapp.com/)
![AWS](https://img.shields.io/badge/AWS-Serverless-orange?style=for-the-badge&logo=amazonaws)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-009688?style=for-the-badge&logo=fastapi)
![DynamoDB](https://img.shields.io/badge/DynamoDB-NoSQL-blue?style=for-the-badge&logo=amazondynamodb)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-black?style=for-the-badge&logo=githubactions)

</p>

---

## 🚀 Overview

The **REX Intelligence API** is a **serverless, multi-tenant backend system** designed for secure financial tracking and analytics.

Built with **FastAPI** and deployed on **AWS Lambda**, the system leverages **DynamoDB** for scalable NoSQL storage and integrates a **CI/CD pipeline** for automated deployments.

> 🔒 **Note:** API endpoints and deployment URLs are intentionally not exposed for security reasons.

---

## 🏗️ Architecture

```bash id="safe1"
Client → API Gateway → Lambda (FastAPI via Mangum) → DynamoDB
                                ↑
                        CI/CD Deployment
```

---

## ✨ Features

* 📊 Multi-user expense tracking
* 🔐 Data isolation using `user_id` (multi-tenant design)
* ⚡ Serverless execution with automatic scaling
* 🧠 Data validation using Pydantic
* 🔄 Safe DynamoDB → JSON serialization
* 🌐 Controlled CORS configuration
* 🚀 Automated CI/CD deployment

---

## 🛠 Tech Stack

### Backend

* FastAPI
* Mangum
* Pydantic
* Boto3

### Cloud Infrastructure

* AWS Lambda
* API Gateway
* DynamoDB
* IAM (Least Privilege Security)

### DevOps

* GitHub Actions (CI/CD)
* Secure credential storage via GitHub Secrets

---

## 📂 Project Structure

```bash id="safe2"
backend/
│
├── main.py
├── requirements.txt
└── .github/workflows/deploy.yml
```

---

## 🔐 Security Design

* Multi-tenant architecture using `user_id` partitioning
* Strict input validation via Pydantic schemas
* CORS restricted to trusted origins
* IAM Least Privilege for database access
* No public exposure of backend endpoints

---

## ⚙️ CI/CD Pipeline

The backend is deployed using an automated **GitHub Actions pipeline**.

### 🔄 Workflow

```bash id="safe3"
Git Push → GitHub Actions → Package → AWS Lambda Deployment
```

---

### 🔐 Secrets Management

Sensitive credentials are stored securely using:

* GitHub Secrets
* IAM Access Policies

> ⚠️ Credentials are never exposed in the repository.

---

## ☁️ Database Design

* DynamoDB (NoSQL)
* Composite Key Structure:

  * Partition Key → `user_id`
  * Sort Key → `id`

### Benefits

* Efficient per-user querying
* Strong data isolation
* Horizontal scalability

---

## 🔮 Future Improvements

* 🔐 OIDC-based authentication (remove static keys)
* 📊 Monitoring & alerting (CloudWatch)
* 📦 Multi-environment deployments
* 🔎 Advanced filtering & analytics

---

## 👨‍💻 Author

**Chinmay V Chatradamath**

---

## 💡 Note

This frontend and backend codebase is private due to security considerations.
Architecture and implementation details are shared at a high level for demonstration purposes.
