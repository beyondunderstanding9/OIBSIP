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

## Project Structure

```text
LOGIN_AUTH/
├── app.py
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
