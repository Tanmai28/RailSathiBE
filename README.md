# RailSathiBE

## 🚀 Overview

**RailSathiBE** is a basic Django REST API project, Dockerized for easy setup and deployment. It features a PostgreSQL database, auto-generated API documentation (Swagger & Redoc), and a simple `items` app for demonstration.

---

## 📦 Features

- Django REST API for managing items
- PostgreSQL database integration
- Dockerized setup with Docker Compose
- Environment variable configuration via `.env`
- Auto-generated API docs (Swagger & Redoc)
- Django admin interface
- Hot-reloading for development
- Database migration and superuser creation via Docker
- Wait-for-it script for reliable startup

---

## 🛠️ Technologies Used

- Python 3.11
- Django 4.x
- Django REST Framework
- PostgreSQL 15
- Docker & Docker Compose
- Swagger/OpenAPI & Redoc

---

## 📝 Setup Instructions

### 1. **Clone the Repository**

```sh
git clone https://github.com/s2pl/RailSathiBE.git
cd RailSathiBE
```

### 2. **Configure Environment Variables**

- Copy `.env.example` to `.env` and fill in any secrets if needed.

```sh
cp .env.example .env
```

### 3. **Build and Run with Docker Compose**

```sh
docker-compose up --build
```

- This will:
  - Build the Django app image
  - Start a PostgreSQL database container
  - Run migrations and start the Django server

### 4. **Create a Superuser (Optional, for Admin Access)**

```sh
docker-compose run web python manage.py createsuperuser
```

---

## 🌐 Accessing the Application

- **API Endpoint:** [http://localhost:8000/items/](http://localhost:8000/items/)
- **Admin Panel:** [http://localhost:8000/admin/](http://localhost:8000/admin/)
- **Swagger Docs:** [http://localhost:8000/swagger/](http://localhost:8000/swagger/)
- **Redoc Docs:** [http://localhost:8000/redoc/](http://localhost:8000/redoc/)

---

## 🧪 API Usage

### **List Items**

```sh
curl -X GET http://localhost:8000/items/
```

### **Create an Item**

```sh
curl -X POST http://localhost:8000/items/ \
  -H "Content-Type: application/json" \
  -d '{"name": "Notebook", "description": "A ruled notebook"}'
```

### **API Endpoints**

| Method | Endpoint         | Description         |
|--------|------------------|--------------------|
| GET    | /items/          | List all items     |
| POST   | /items/          | Create a new item  |
| ...    | ...              | ...                |

- See Swagger/Redoc for full, interactive API documentation.

---

## ⚙️ Project Structure

```
RailSathiBE/
├── Dockerfile
├── docker-compose.yml
├── .env.example
├── wait-for-it.sh
├── items/
│   └── ... (Django app code)
├── railsathibe/
│   └── ... (Django project code)
└── README.md
```

---

## ⚠️ Assumptions & Design Decisions

- The project is intended for development/demo use.
- All configuration is via environment variables for security and flexibility.
- Database credentials are set in `.env` and passed to both Django and PostgreSQL.
- Hot-reloading is enabled via Docker volume mounts.
- The `wait-for-it.sh` script ensures the database is ready before Django starts.

---

## 🐳 Dockerization Details

- **Dockerfile**: Uses official Python image, installs dependencies, copies code, runs migrations, and starts the server.
- **docker-compose.yml**: Defines two services (`web` for Django, `db` for PostgreSQL), sets up networking, and mounts code for live reload.
- **wait-for-it.sh**: Ensures Django waits for the database to be ready before starting.

---

## 🏁 Running Locally Without Docker (Optional)

1. Create a virtual environment and activate it.
2. Install dependencies: `pip install -r requirements.txt`
3. Set up PostgreSQL locally and update `railsathibe/settings.py` accordingly.
4. Run migrations: `python manage.py migrate`
5. Start the server: `python manage.py runserver`

---
