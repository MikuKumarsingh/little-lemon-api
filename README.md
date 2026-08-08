# Little Lemon Web Application

Meta Back-End Developer Capstone – Little Lemon Web Application.

This project is organized around the requirements of the Coursera capstone: a Django web server, MySQL database support, static/template-driven pages, a menu API, a secured table-booking API, user registration/authentication, unit tests, and API testing with Insomnia.

## Features

- Django web pages at `/`, `/menu/`, and `/book/`
- MySQL database configuration
- Django REST Framework
- Menu API with CRUD operations
- Table Booking API with CRUD operations
- Token authentication
- Djoser user registration/login/logout endpoints
- Unit tests
- Django admin

## Setup

### 1. Create and activate a virtual environment

```bash
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. MySQL configuration (course submission)

Create a MySQL database named `littlelemon_db`. Then set these environment variables:

```text
MYSQL_DATABASE=littlelemon_db
MYSQL_USER=root
MYSQL_PASSWORD=your_mysql_password
MYSQL_HOST=127.0.0.1
MYSQL_PORT=3306
```

The project defaults to MySQL because MySQL is part of the capstone requirements.

### 4. Easy local smoke test with SQLite

If MySQL is not available on your computer, set:

```text
USE_SQLITE=true
```

Then run:

```bash
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Use SQLite only as a local convenience. The submission settings contain the MySQL configuration required by the course.

## API endpoints

### Menu

- `GET /api/menu/`
- `POST /api/menu/`
- `GET /api/menu/<id>/`
- `PUT /api/menu/<id>/`
- `PATCH /api/menu/<id>/`
- `DELETE /api/menu/<id>/`

Aliases are also available under `/api/menu/items/`.

### Table booking

Table bookings are protected with token/session authentication:

- `GET /api/booking/tables/`
- `POST /api/booking/tables/`
- `GET /api/booking/tables/<id>/`
- `PUT /api/booking/tables/<id>/`
- `PATCH /api/booking/tables/<id>/`
- `DELETE /api/booking/tables/<id>/`

Example booking JSON:

```json
{
  "name": "Miku",
  "no_of_guests": 2,
  "booking_date": "2030-01-10",
  "booking_time": "19:00:00"
}
```

### Authentication

Djoser provides:

- `POST /auth/users/` – register
- `POST /auth/token/login/` – obtain token
- `POST /auth/token/logout/` – logout
- `GET /auth/users/me/` – current user

For a booking request using token authentication, add:

```text
Authorization: Token <your-token>
```

## Testing

Run:

```bash
python manage.py test
```

The tests cover menu API behavior, booking authentication, booking creation, and booking update behavior.

## Insomnia checklist

1. Register a user with `POST /auth/users/`.
2. Obtain a token with `POST /auth/token/login/`.
3. Send the token in the `Authorization` header.
4. Test GET/POST/PUT/PATCH/DELETE on `/api/booking/tables/`.
5. Test GET/POST/PUT/PATCH/DELETE on `/api/menu/`.

## Git

Commit the complete project structure, not individual settings files only. Do not commit passwords, tokens, or `.env` files.
