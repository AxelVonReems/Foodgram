# Foodgram - Recipe Assistant

Foodgram is a web service for finding and sharing recipes. Users can view and create recipes, subscribe to their favorite authors, and add recipes to their favorites list, including a feature to download a shopping list in `.txt` format.

## Admin Credentials

- Email: admin@example.com
- Password: admin
- Project URL: http://51.250.23.204

## Tech Stack

[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
[![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-464646?style=flat-square&logo=PostgreSQL)](https://www.postgresql.org/)
[![Nginx](https://img.shields.io/badge/-NGINX-464646?style=flat-square&logo=NGINX)](https://nginx.org/ru/)
[![gunicorn](https://img.shields.io/badge/-gunicorn-464646?style=flat-square&logo=gunicorn)](https://gunicorn.org/)
[![docker](https://img.shields.io/badge/-Docker-464646?style=flat-square&logo=docker)](https://www.docker.com/)
[![GitHub%20Actions](https://img.shields.io/badge/-GitHub%20Actions-464646?style=flat-square&logo=GitHub%20actions)](https://github.com/features/actions)
[![Yandex.Cloud](https://img.shields.io/badge/-Yandex.Cloud-464646?style=flat-square&logo=Yandex.Cloud)](https://cloud.yandex.ru/)

## How to Run the Project Locally

Clone the repository and navigate to it via the command line:

```text
[https://github.com/AxelVonReems/foodgram-project-react](https://github.com/AxelVonReems/foodgram-project-react)
```

Navigate to the project folder:

```bash
cd foodgram-project-react
```

Create and activate a virtual environment:

```bash
WIN: python -m venv venv
MAC: python3 -m venv venv
```

```bash
WIN: source venv/scripts/activate
MAC: source venv/bin/activate
```

Install dependencies from the `requirements.txt` file:

```bash
WIN: python -m pip install --upgrade pip
MAC: python3 -m pip install --upgrade pip
```

```bash
pip install -r requirements.txt
```

In the `settings.py` file, replace the PostgreSQL database with SQLite3 by following the inline comments.

Apply migrations:

```bash
WIN: python manage.py makemigrations  
MAC: python3 manage.py makemigrations
```

```bash
WIN: python manage.py migrate --noinput
MAC: python3 manage.py migrate --noinput
```

Start the server:

```bash
WIN: python manage.py runserver
MAC: python3 manage.py runserver
```

The service will be available at: http://127.0.0.1:8000/

## How to Run the Project Using Docker

Clone the repository and navigate to it via the command line.

Navigate to the project folder.

Create and activate a virtual environment.

Install dependencies from the `requirements.txt` file.

In the `infra` folder, create and populate a `.env` file using the following template:

```env
DB_ENGINE=django.db.backends.postgresql - specifies that we are working with PostgreSQL
DB_NAME=postgres - database name
POSTGRES_USER=postgres - login for database connection
POSTGRES_PASSWORD=postgres - password for database connection
DB_HOST=db - service (container) name
DB_PORT=5432 - port for database connection 
SECRET_KEY=XXXXXXXXXXXXXXXXX - Django project secret key
DEBUG='False' - debugger setting
```

Build and start the container using Docker Compose:

```bash
docker-compose build
docker-compose up
```

Apply migrations via Docker Compose:

```bash
docker-compose exec web python manage.py makemigrations
docker-compose exec web python manage.py migrate --noinput
```

Load ingredients and tags:

```bash
docker-compose exec web python manage.py load_ingrs
docker-compose exec web python manage.py load_tags
```

Collect static files:

```bash
docker-compose exec web python manage.py collectstatic --no-input
```

Create a superuser via Docker Compose:

```bash
docker-compose exec web python manage.py createsuperuser
```

## Author

Aleksei Smirnov. GitHub: https://github.com/AxelVonReems/
