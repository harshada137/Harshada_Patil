# 🐳 Docker Assessment Project

This repository contains a **Dockerized application** created as part of a Docker assessment.
The project demonstrates containerization using **Docker and Docker Compose** and can be executed easily on any system with Docker installed.

---

## 📌 Project Overview

* Fully containerized application
* Uses **Docker** and **Docker Compose**
* Easy one-command execution
* Platform independent (Linux / macOS / Windows with WSL)

---

## 📂 Repository Structure

```
Docker-Assesment/
│
├── templates/             # HTML templates directory
│   └── index.html         # Main frontend page
│
├── app.py                 # Python application entry point
├── requirements.txt       # Python dependencies
├── message.sql            # Database SQL script
│
├── Dockerfile             # Docker image configuration
├── docker-compose.yml     # Multi-container orchestration
│
├── .dockerignore          # Docker ignore rules
├── .gitignore             # Git ignore rules
│
├── execution.md           # Step-by-step execution guide
└── README.md              # Project documentation

```

---

## ⚙️ Prerequisites

Make sure the following tools are installed on your system:

* **Git**
* **Docker**
* **Docker Compose**

Check versions using:

```bash
git --version
docker --version
docker compose version
```

---

## 🚀 How to Run the Project

### Step 1: Clone the Repository

```bash
git clone https://github.com/harshada137/Docker-Assesment.git
cd Docker-Assesment
```

### Step 2: Build and Start Containers

```bash
docker compose up --build
```

🔹 This command will build the Docker images and start all required containers.

### Step 3: Access the Application

Open your browser and navigate to:

```
http://localhost:<PORT>
```

➡️ Replace `<PORT>` with the port exposed in `docker-compose.yml`.

---

## 🧪 Useful Docker Commands

Check running containers:

```bash
docker ps
```

View logs:

```bash
docker compose logs
```

Stop containers:

```bash
docker compose down
```

Stop containers and remove volumes:

```bash
docker compose down -v
```

---

## 📄 Execution Guide

For a **detailed step-by-step execution guide**, refer to:

📘 **`EXECUTION.md`**

---

## ✅ Key Highlights

* No manual dependency installation required
* Easy setup with Docker Compose
* Clean and reusable configuration
* Suitable for assessments and interviews

---

## 👩‍💻 Author

**Harshada Patil**
Docker Assessment 
