# 🚀 EXECUTION.md

**Docker Assessment – Execution Guide**

This document explains how to **clone, build, and run** the Docker Assessment project on any local machine.

---

## 📌 Prerequisites

Before starting, ensure the following tools are installed on your system:

* **Git**
* **Docker**
* **Docker Compose**

Verify installation using:

```bash
git --version
docker --version
docker compose version
```

---

## 📥 Step 1: Clone the Repository

Clone the project from GitHub:

```bash
git clone https://github.com/harshada137/Docker-Assesment.git
```

Move into the project directory:

```bash
cd Docker-Assesment
```

---

## 📂 Step 2: Review Project Files

Ensure the following important files exist:

* `Dockerfile` (if used)
* `docker-compose.yml`
* Application source code
* `.env` (if required)

If an `.env` file is required and not present, create it based on `.env.example` (if provided).

---

## 🛠️ Step 3: Build and Run the Application

Use Docker Compose to build images and start containers:

```bash
docker compose up --build
```

🔹 This command will:

* Build Docker images
* Create required containers
* Start all services

---

## ▶️ Step 4: Run in Detached Mode (Optional)

To run containers in the background:

```bash
docker compose up -d --build
```

---

## 🌐 Step 5: Access the Application

Once containers are running, access the application using:

```
http://localhost:<PORT>
```

📌 Replace `<PORT>` with the port exposed in `docker-compose.yml`.

---

## 🧪 Step 6: Verify Running Containers

Check running containers:

```bash
docker ps
```

Check logs (if needed):

```bash
docker compose logs
```

---

## 🛑 Step 7: Stop the Application

To stop and remove containers:

```bash
docker compose down
```

To remove volumes as well:

```bash
docker compose down -v
```

---

## 🧹 Optional Cleanup

Remove unused images and containers:

```bash
docker system prune
```

---

## ✅ Notes

* This project is fully containerized using Docker.
* No manual dependency installation is required on the host system.
* Works on **Linux, macOS, and Windows (WSL)**.

---

## 👤 Author

**Harshada Patil**
Docker Assessment 
