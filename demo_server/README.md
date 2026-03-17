# Demo API Server

Standalone Flask HTTP API. No dependencies on test frameworks or other projects.

## Run

```bash
pip install -r requirements.txt
python app.py
```

Listens on `http://0.0.0.0:5000`.

## API

| Method | Path | Auth | Description |
|--------|------|------|-------------|
| GET | /health | No | Health check → `{"status": "ok"}` |
| GET | /users | No | List users → `{"users": [...]}` |
| GET | /users/{id} | No | Get user by ID → 200 or 404 |
| POST | /login | No | Body: `{"email","password"}` → `{"token","user_id"}` or 401 |
| GET | /me | Yes | Header: `Authorization: Bearer <token>` → user info or 401 |

**Valid login**: `alice@test.com` / `secret123` → returns `token-alice-123`.
