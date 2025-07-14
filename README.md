# RailSathiBE

## 🚀 Setup Instructions

1. Clone the repo:
   ```
   git clone https://github.com/yourusername/RailSathiBE.git
   cd RailSathiBE
   ```
2. Copy `.env.example` to `.env` and fill in secrets.
3. Build and run:
   ```
   docker-compose up --build
   ```
4. Access:
   - API: [http://localhost:8000/items/](http://localhost:8000/items/)
   - Admin: [http://localhost:8000/admin/](http://localhost:8000/admin/)
   - Swagger: [http://localhost:8000/swagger/](http://localhost:8000/swagger/)
   - Redoc: [http://localhost:8000/redoc/](http://localhost:8000/redoc/)

## 🧩 Features

- Django REST API for items
- PostgreSQL database
- Dockerized setup
- Swagger & Redoc API docs
- Django admin

## ⚠️ Assumptions & Design

- Uses default Django settings for development.
- PostgreSQL is used as the database.
- Environment variables are used for configuration.

## 📋 API Endpoints

- `GET /items/` - List items
- `POST /items/` - Create item
- ... (add more as needed)
