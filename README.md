# 🚗 Vehicle Data MLOps Project

> A comprehensive, end-to-end MLOps pipeline for vehicle data management, leveraging modern tools and cloud services to build, validate, deploy, and monitor machine learning models seamlessly.

---

## 🛠️ Project Overview

This project automates the lifecycle of machine learning models—from data ingestion and validation to model training, evaluation, and deployment—powered by a robust infrastructure using **MongoDB Atlas**, **AWS S3**, **Docker**, **GitHub Actions CI/CD**, and more. It’s built for scalability, reliability, and production readiness.

---

## ⚡ Key Features

* **Automated Data Ingestion & Storage** with MongoDB Atlas
* **Robust Data Validation & Transformation** using custom schemas
* **Feature Engineering & Exploratory Data Analysis (EDA)** notebooks included
* **Modular, Config-Driven Pipeline Components** for ingestion, validation, training, evaluation, and deployment
* **Model Evaluation & Versioning** with automated threshold checks
* **Cloud Storage Integration** using AWS S3 for model registry
* **End-to-End CI/CD Pipeline** with Docker containers, GitHub Actions, and AWS EC2 self-hosted runners
* **Live Web Application** for predictions with a Flask backend and React-like frontend setup
* **Comprehensive Logging & Exception Handling** for traceability and reliability

---

## 🧰 Technologies & Tools

| Category                 | Tools / Frameworks                      |
| ------------------------ | --------------------------------------- |
| **Programming**          | Python 3.10, Jupyter Notebooks          |
| **Package Management**   | pip, conda, setup.py, pyproject.toml    |
| **Data Storage**         | MongoDB Atlas (Cloud NoSQL DB)          |
| **Cloud Services**       | AWS S3, AWS EC2, AWS IAM                |
| **Containerization**     | Docker                                  |
| **CI/CD**                | GitHub Actions, Self-hosted Runners     |
| **Web Framework**        | Flask (Backend), HTML/CSS/JS (Frontend) |
| **Logging & Monitoring** | Custom logger and exception handlers    |
| **Version Control**      | Git, GitHub                             |

---

## 🚀 Getting Started

### 1. Project Setup

```bash
# Create project template
python template.py

# Setup environment and install dependencies
conda create -n vehicle python=3.10 -y
conda activate vehicle
pip install -r requirements.txt

# Verify installed packages
pip list
```

---

### 2. MongoDB Atlas Setup

* Sign up and create a free cluster (M0 tier).
* Configure network access (`0.0.0.0/0`) for remote connection.
* Create a DB user with username and password.
* Obtain the MongoDB connection string (Python driver, version 3.6+).
* Save your connection string securely (replace password placeholder).

### 3. Data Management

* Add your dataset inside the `notebook` folder.
* Use `mongoDB_demo.ipynb` to push and verify data in MongoDB.
* Data is stored in key-value format, accessible for ingestion and further processing.

---

### 4. Pipeline Components

| Component               | Description                                                         |
| ----------------------- | ------------------------------------------------------------------- |
| **Data Ingestion**      | Fetch data from MongoDB, convert to Pandas DataFrame                |
| **Data Validation**     | Validate data schema, ensure data quality                           |
| **Data Transformation** | Feature scaling, encoding, and estimator setup                      |
| **Model Training**      | Train ML models with configurable hyperparameters                   |
| **Model Evaluation**    | Evaluate model performance, compare with baseline, apply thresholds |
| **Model Pusher**        | Push models to AWS S3 model registry for version control            |
| **Prediction Pipeline** | Serve predictions via web API                                       |

---

### 5. AWS Configuration

* Create IAM user with AdministratorAccess.
* Generate and set AWS Access Key & Secret Access Key as environment variables.
* Create S3 bucket `my-model-mlopsproj` in `us-east-1` region.
* Integrate AWS S3 storage in the project for model management.

---

### 6. CI/CD Setup

* Dockerize the application using `Dockerfile` and `.dockerignore`.
* Setup GitHub Actions workflows (`aws.yaml`) for build and deploy.
* Configure AWS ECR repository for storing Docker images.
* Launch EC2 Ubuntu instance to host app and connect GitHub self-hosted runner.
* Expose app on EC2 instance port `5080` and access via public IP.

---

## 🗂️ Project Structure (Highlight)

```
├── notebook/
│   └── mongoDB_demo.ipynb
├── src/
│   ├── components/
│   ├── configuration/
│   │   ├── aws_connection.py
│   │   └── mongo_db_connections.py
│   ├── data_access/
│   ├── entity/
│   │   ├── config_entity.py
│   │   ├── artifact_entity.py
│   │   └── s3_estimator.py
│   ├── pipeline/
│   ├── app.py
├── Dockerfile
├── requirements.txt
├── setup.py
├── pyproject.toml
└── .github/workflows/aws.yaml
```

---

## 📚 Additional Information

* Detailed EDA and feature engineering notebooks available in the `notebook` folder.
* Logging and exception handling tested and integrated for production robustness.
* Environment variables management includes MongoDB URL and AWS credentials.
* `.gitignore` excludes sensitive files such as `artifact` directory and environment files.

---

## 👨‍💻 How to Use

1. Setup your environment and install dependencies.
2. Configure MongoDB Atlas and AWS credentials.
3. Run `demo.py` to test pipeline components end-to-end.
4. Use the web app (`app.py`) to serve live predictions.
5. Push code changes to trigger CI/CD pipeline and deploy updated containers automatically.

---

## 📞 Contact & Collaboration

For questions, demos, or collaboration opportunities, feel free to reach out!

---

*Thank you for reviewing this project — a fully featured MLOps pipeline showcasing best practices for scalable machine learning production.*
