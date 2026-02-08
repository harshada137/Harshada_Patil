# 🏗️ Architecture of the Docker Assessment Project

This project follows a **simple web application architecture** with **Python backend**, **HTML frontend**, and **Docker containerization**. Here’s a visual and logical breakdown.

---

## 1️⃣ Overall Components

```
+--------------------+          +-----------------+
|   User / Browser   |  <---->  |  Web Application|
+--------------------+          +-----------------+
                                      |
                                      v
                             +------------------+
                             |  Python Backend  |
                             |   (app.py)       |
                             +------------------+
                                      |
                                      v
                             +------------------+
                             | Templates / HTML |
                             |   (index.html)   |
                             +------------------+
                                      |
                                      v
                             +------------------+
                             |    Database      |
                             |  (message.sql)   |
                             +------------------+
```

---

## 2️⃣ Components Explained

### **1. Frontend**

* **Folder:** `templates/`
* **File:** `index.html`
* **Purpose:**
  Provides the user interface of the application.
  Rendered by the Python backend using a templating engine (likely Flask/Jinja2).

---

### **2. Backend**

* **File:** `app.py`
* **Purpose:**

  * Serves HTTP requests from users.
  * Renders HTML templates.
  * Connects to the database to fetch/store messages (based on `message.sql`).
* **Framework:** Python (Flask assumed because of templates).

---

### **3. Database**

* **File:** `message.sql`
* **Purpose:**

  * Contains SQL commands to initialize the database (tables, seed data).
  * Used by the backend to persist data.
* **Database Type:** MySQL (most common in Docker assessments with SQL scripts).

---

### **4. Dockerization**

* **Dockerfile:**

  * Builds a Docker image for the Python application.
  * Installs dependencies listed in `requirements.txt`.
  * Copies source code and templates into the container.
  * Sets the entry point to run `app.py`.

* **docker-compose.yml:**

  * Defines services (e.g., `app` and `db`).
  * Links the application container with the database container.
  * Configures volumes, ports, and networks for easy access.

---

### **5. Ignore Files**

* **.dockerignore:** Prevents unnecessary files (e.g., `.git`, `__pycache__`) from being copied into the Docker image.
* **.gitignore:** Prevents local or sensitive files from being committed to GitHub.

---

## 3️⃣ Flow of the Application

1. **User requests the web page** → Browser sends HTTP request to containerized Python backend.
2. **Backend receives request** → `app.py` processes the request.
3. **Backend interacts with database** → Executes SQL queries from `message.sql` or connects to the running database container.
4. **Backend renders HTML templates** → Sends the populated `index.html` back to the browser.
5. **User sees the page** → Can interact (submit forms/messages), which again goes through the backend and database.

---

![Web-Page](images/arch.png) 

## 4️⃣ Docker Network & Ports

* **Network:** Docker Compose automatically creates a bridge network so services can communicate.
  Example: `app` container communicates with `db` container using the service name.
* **Ports:** Exposed in `docker-compose.yml` so the app is accessible on `localhost:<PORT>`.

---

## 5️⃣ Key Points / Benefits of this Architecture

* **Separation of concerns:** Frontend, backend, and database are isolated.
* **Portability:** Can run on any machine with Docker without manual dependency setup.
* **Scalability:** Adding more services (like Redis, Celery, etc.) is easy with Docker Compose.
* **Maintainability:** Clear folder structure makes it easy to understand and extend.


