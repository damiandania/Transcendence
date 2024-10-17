<p>
<img src="https://github.com/damiandania/damiandania/blob/main/Pics/Transcendence.png"
	alt="Project pic" width="150" height="150"/>
</p>

# Transcendence 🚀

The ft_transcendence project is a team project from 42 school, where the goal is to develop a website that allows users to create accounts via the 42 API, play real-time multiplayer games of Pong, and we added a second game called Invaders.

This project is built using the following technologies:

- Docker & Docker Compose
- Django
- JavaScript
- PostgreSQL

We are still working in this project! 👷🏻‍♂️

# Django Project Overview

## Project Structure

```bash
├── mywebsite/
│   ├── frontend/
│   │   ├── static/
│   │   │   └── css/
│   │   │   └── img/
│   │   │   └── js/
│   │   │   └── node_modules/
│   │   │   └── sass/
│   │   │   └── video/
│   │   ├── templates/
│   │   │   └── base.html
│   │   │   └── home.html
│   │   │   └── login.html
│   │   │   └── signup.html
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── forms.py
│   │   ├── models.py
│   │   ├── test.py
│   │   ├── urls.py
│   │   └── views.py
│   ├── mywebsite/
│   │   ├── __init__.py
│   │   ├── asgi.py
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── staticfiles/
│   ├── Dockerfile
│   ├── entrypoint.sh
│   ├── manage.py
│   └── requirements.txt
│── nginx
│   ├── Dockerfile
│   └── nginx.conf
├── .env
├── .gitignore
├── docker-compose.yml
├── Makefile
└── README.md
```

- **Outer `mysite/` Directory**:
  - This is the container for your project. Its name does not matter to Django; you can rename it to anything you like.

- **`manage.py`**:
  - A command-line utility that lets you interact with this Django project in various ways. You can read more about `manage.py` in [django-admin and manage.py](https://docs.djangoproject.com/en/stable/ref/django-admin/).

- **Inner `mysite/` Directory**:
  - This directory is the actual Python package for your project. Its name is the Python package name you’ll need to use to import anything inside it (e.g., `mysite.urls`).

- **`mysite/__init__.py`**:
  - An empty file that tells Python that this directory should be considered a Python package. For more details on Python packages, you can read the [official Python documentation](https://docs.python.org/3/tutorial/modules.html#packages).

- **`mysite/settings.py`**:
  - Contains settings/configuration for this Django project. For more information on how settings work, refer to [Django settings](https://docs.djangoproject.com/en/stable/topics/settings/).

- **`mysite/urls.py`**:
  - Defines the URL declarations for this Django project; essentially, it serves as a "table of contents" for your Django-powered site. You can read more about URL dispatchers in the [URL dispatcher](https://docs.djangoproject.com/en/stable/topics/http/urls/) documentation.

- **`mysite/asgi.py`**:
  - An entry-point for ASGI-compatible web servers to serve your project. For details on deploying with ASGI, see [How to deploy with ASGI](https://docs.djangoproject.com/en/stable/howto/deployment/asgi/).

- **`mysite/wsgi.py`**:
  - An entry-point for WSGI-compatible web servers to serve your project. For more information, refer to [How to deploy with WSGI](https://docs.djangoproject.com/en/stable/howto/deployment/wsgi/).

## Environment Variables

To ensure that your Django project runs correctly, you need to set up a `.env` file with the appropriate environment variables. This file should be placed in the root directory of your project and should include the following variables:

DEBUG=True
SECRET_KEY= #look in settings.py
DJANGO_ALLOWED_HOSTS=localhost "ipadress1" "ipadress2"...
SQL_ENGINE=django.db.backends.postgresql
SQL_DATABASE=your_db_name
SQL_USER=your_db_user
SQL_PASSWORD=your_db_password
SQL_HOST=your_db_host
SQL_PORT=5432
DATABASE=postgres

POSTGRES_DB=your_db_name
POSTGRES_USER=your_db_user
POSTGRES_PASSWORD=your_db_password

CLIENT_ID=
CLIENT_SECRET=
API_42_REDIRECT_URI=
API_42_AUTH_URL=

Replace `your_db_user`, `your_db_password`, `your_db_name`, and `your_db_host` with your actual database credentials and host information.

## Additional Notes

- Do not commit your `.env` file to version control systems like Git. Add `.env` to your `.gitignore` file to keep sensitive information secure.

For more information on managing environment variables in Django, refer to the [Django documentation on settings](https://docs.djangoproject.com/en/stable/topics/settings/)


## Useful Commands

### Setting Up Your Virtual Environment

```bash
python -m venv DirectoryName
source DirectoryName/bin/activate
deactivate
```

### Instaliing Django

```bash
python -m pip install django
python -m django --version
```

### Starting a New Django Project

```bash
django-admin startproject siteName
```

### Running the Development Server

```bash
cd siteName
python manage.py runserver

```

### Creating a New Django App

```bash
python manage.py startapp appName
```

### Working with Migrations

#### After Changing Models

```bash
python manage.py makemigrations appName
```

#### Viewing SQL for a Migration

```bash
python manage.py sqlmigrate appName 0001
```

#### Checking for Project Problems

```bash
python manage.py check
```

#### Applying Migrations

```bash
python manage.py migrate
```

#### Creating a Superuser for Admin Interface

```bash
python manage.py createsuperuser
```

python manage.py test appName

python -m pip install coverage
coverage run --source='.' manage.py test appName
coverage report
