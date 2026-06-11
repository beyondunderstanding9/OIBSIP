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

Then open:

```text
http://127.0.0.1:5000
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

## GitHub Workflow

```bash
git init
git add .
git commit -m "Create Flask login authentication system"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

## How It Works

`app.py` is the main Flask application. It defines the routes, connects to SQLite, hashes passwords, stores login sessions, and protects the dashboard page.

- `get_db()` opens a SQLite database connection for the current request.
- `init_db()` creates the `users` table if it does not already exist.
- `/register` validates form data, hashes the password, and saves the user.
- `/login` checks the username and password hash, then stores the user id in the session.
- `/dashboard` uses `@login_required`, so only logged-in users can open it.
- `/logout` clears the session and returns the user to the home page.

## Interview Explanation

I built a simple authentication system using Python Flask. My contribution was creating the complete flow: user registration, password hashing, login validation, session handling, logout, and a protected dashboard page. I also connected the project to GitHub and prepared it for deployment on Vercel.

The main logic is that passwords are never stored directly. During registration, the password is converted into a secure hash using Werkzeug. During login, the entered password is compared with the saved hash. If it matches, the user id is stored in Flask's session. The secured dashboard checks that session before allowing access.
