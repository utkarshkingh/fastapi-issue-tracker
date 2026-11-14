# fastapi-issue-tracker

A REST API that tracks issues. It shows the core FastAPI features: routing, Pydantic validation, CRUD, middleware, and file storage.

This is a fork of [bradtraversy/fastapi-issue-tracker](https://github.com/bradtraversy/fastapi-issue-tracker). It is the project from the [FastAPI Crash Course](https://youtu.be/8TMQcRcBnW8).

## Overview

| Item       | Detail                                       |
| ---------- | -------------------------------------------- |
| Stack      | Python 3.9+, FastAPI, Pydantic               |
| Storage    | JSON file (`data/issues.json`)               |
| Priority   | `low`, `medium`, `high`                      |
| Status     | `open`, `in_progress`, `closed`              |
| Middleware | Request timing, CORS                         |

## Endpoints

| Method | Path                  | Action             |
| ------ | --------------------- | ------------------ |
| GET    | `/api/v1/health`      | Health check       |
| GET    | `/api/v1/issues`      | List all issues    |
| GET    | `/api/v1/issues/{id}` | Get one issue      |
| POST   | `/api/v1/issues`      | Create an issue    |
| PUT    | `/api/v1/issues/{id}` | Update an issue    |
| DELETE | `/api/v1/issues/{id}` | Delete an issue    |

## Contents

| Path                | Purpose                         |
| ------------------- | ------------------------------- |
| `main.py`           | App, CORS, health check         |
| `app/routes/`       | Issue endpoints                 |
| `app/schemas.py`    | Pydantic models                 |
| `app/storage.py`    | Read and write the JSON file    |
| `app/middleware/`   | Timing middleware               |
| `docs/`             | Crash course notes and diagram  |

## Run

```bash
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install "fastapi[standard]"
fastapi dev main.py
```

The API starts on `http://localhost:8000`. Open `/docs` (Swagger UI) or `/redoc`.
