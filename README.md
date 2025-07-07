---

## 📦 Three-Tier Dockerized Application

This repository contains a simple **three-tier web application** that includes:

* 🖥️ Frontend: A  React app
* ⚙️ Backend: A Node.js/Express API
* 🗄️ MongoDB: A NoSQL database

All services are containerized using Docker and orchestrated with Docker Compose.

---

### 🧱 Project Structure

```
.
├── backend/
│   ├── Dockerfile
│   ├── .env
│   └── (backend source files)
├── frontend/
│   ├── Dockerfile
│   ├── .env
│   └── (frontend source files)
├── docker-compose.yml
```

---

### 🚀 Getting Started

#### 1. Clone the Repository

```bash
git clone https://github.com/shoeb5401/Docker-Three-Tier-Javascript.git
cd Docker-Three-Tier-Javascript
```

#### 2. Setup Environment Variables

Ensure `.env` files are present in both the `frontend/` and `backend/` directories.

Example `.env` for backend:

```env
MONGO_USERNAME=admin
MONGO_PASSWORD=admin123
MONGO_DATABASE=mydb
MONGO_CONN_STR=mongodb://admin:admin123@mongodb:27017/mydb
USE_DB_AUTH=true
PORT=8000
```

Example `.env` for frontend:

```env
REACT_API_URL=http://localhost:5000/api
```

#### 3. Start All Services

```bash
docker-compose up --build
```

This will:

* Build the images for frontend and backend
* Start MongoDB and initialize the database
* Health-check MongoDB and the backend before the frontend starts

#### 4. Access the App

* Frontend: [http://localhost:5173](http://localhost:5173)
* Backend API: [http://localhost:5000](http://localhost:5000)
* MongoDB: `localhost:27017`

---

### 🛑 Stop and Remove Containers

```bash
docker-compose down -v --remove-orphans
```

---

### ✅ Healthchecks

* **MongoDB**: Pings the server using `mongosh` to ensure it's ready.
* **Backend**: Exposes a health route (`/ok`) to verify service readiness.

---

### 🧪 Notes

* Make sure Docker is installed and running.
* Use `docker ps` and `docker logs <container>` for debugging if needed.

---

