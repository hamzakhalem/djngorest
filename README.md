# Django REST Auth Starter

A minimal Django REST Framework setup with token authentication through [Djoser](https://djoser.readthedocs.io/). It's a learning project and a starting point for an API that needs sign-up and login.

## Features

- User registration, login and logout with Djoser
- Token authentication (`rest_framework.authtoken`)
- CORS enabled with `django-cors-headers`, so a separate frontend can call the API

## API

| Method | Endpoint | Description |
| --- | --- | --- |
| POST | `/api/v1/users/` | Register a user |
| GET | `/api/v1/users/me/` | Current user (token required) |
| POST | `/api/v1/token/login/` | Log in and get a token |
| POST | `/api/v1/token/logout/` | Log out (token required) |

Send the token as `Authorization: Token <token>`.

## Built with

- Python 3, Django, Django REST Framework
- Djoser, django-cors-headers
- SQLite

## Run it locally

```bash
git clone https://github.com/hamzakhalem/djngorest.git
cd djngorest
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install django djangorestframework djoser django-cors-headers
export DJANGO_SECRET_KEY="any-long-random-string"   # PowerShell: $env:DJANGO_SECRET_KEY="..."
cd main
python manage.py migrate
python manage.py runserver
```

## Project structure

```
main/   Django project: settings and URLs (Djoser routes)
api/    Early work on a first model and serializer
```
