# Login Authentication System

A simple Python Flask project that allows users to register, log in, log out, and access a secured dashboard page.

## Features

- User registration
- Password hashing
- User login and logout
- Session-based authentication
- Protected dashboard route
- SQLite database

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python app.py
```

## Live Website

The project is deployed on Vercel:

https://login-auth-jyo.vercel.app/

## Project Structure

```text
LOGIN_AUTH/
├── app.py
├── .python-version
├── requirements.txt
├── templates/
│   ├── base.html
│   ├── home.html
│   ├── register.html
│   ├── login.html
│   └── dashboard.html
└── static/
    └── styles.css
```

## How It Works

`app.py` is the main Flask application. It defines the routes, connects to SQLite, hashes passwords, stores login sessions, and protects the dashboard page.

- `get_db()` opens a SQLite database connection for the current request.
- `init_db()` creates the `users` table if it does not already exist.
- `/register` validates form data, hashes the password, and saves the user.
- `/login` checks the username and password hash, then stores the user id in the session.
- `/dashboard` uses `@login_required`, so only logged-in users can open it.
- `/logout` clears the session and returns the user to the home page.
