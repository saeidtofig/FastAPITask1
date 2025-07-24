
# ✅ Task Tracker API

A **FastAPI**-based task management API with user authentication, **PostgreSQL** database support, **JWT-based login**, and **Docker** integration.

---

## 🚀 Features

- 🔐 JWT-based authentication (`/token`)
- 👤 User registration (`/users/`)
- ✅ CRUD for Tasks (`/tasks/`)
- 🗄️ PostgreSQL integration
- 🐳 Docker support (with Compose)
- 🌐 CORS enabled for frontend connection

---

## 📁 Project Structure

```
.
├── app/
│   ├── __init__.py
│   ├── main.py            # FastAPI app with routes and CORS
│   ├── database.py        # SQLAlchemy DB setup
│   ├── models.py          # DB models: User & Task
│   ├── schemas.py         # Pydantic schemas for request/response
│   ├── auth.py            # JWT and password hashing logic
│   └── routers/
│       └── tasks.py       # Routes for tasks (GET, POST)
│
├── Dockerfile             # Docker setup for FastAPI
├── docker-compose.yml     # Docker Compose with PostgreSQL
├── requirements.txt       # Dependencies
├── .env                   # Environment config (DB URL)
└── README.md              # You are here!
```

---

## 🛠️ Endpoints

### 🔑 Auth

- `POST /token` – Login with OAuth2 credentials (returns JWT token)
- `POST /users/` – Register a new user

### ✅ Tasks (Authenticated)

- `POST /tasks/` – Create task
- `GET /tasks/` – Get your tasks

---

## 📦 Setup Instructions

### ▶️ 1. Run with Docker (Recommended)

> Make sure Docker & Docker Desktop are installed.

```bash
docker-compose up --build
```

🔗 Visit: [http://localhost:8000/docs](http://localhost:8000/docs)

### 🧪 2. Run Locally without Docker

#### Step 1: Create and activate a virtual environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

#### Step 2: Install dependencies
```bash
pip install -r requirements.txt
```

#### Step 3: Start PostgreSQL database
> You must have PostgreSQL running locally and update `.env`:
```env
DATABASE_URL=postgresql://username:password@localhost:5432/tasks
```

#### Step 4: Run the app
```bash
uvicorn app.main:app --reload
```

---

## 🔒 Authentication Flow

1. Register via `/users/`
2. Login via `/token` (returns JWT)
3. Use `Authorization: Bearer <token>` in headers to access `/tasks/` endpoints.

---

## 🧱 Technologies

- [FastAPI](https://fastapi.tiangolo.com/)
- [SQLAlchemy](https://www.sqlalchemy.org/)
- [PostgreSQL](https://www.postgresql.org/)
- [Docker](https://www.docker.com/)
- [JWT](https://jwt.io/)
- [Pydantic](https://pydantic-docs.helpmanual.io/)
- [Uvicorn](https://www.uvicorn.org/)

---

## 🤝 Contributing

Feel free to fork and PR improvements or bug fixes.

---

## 📜 License

© 2025 [Saeid Tofighi](https://github.com/saeidtofig)
