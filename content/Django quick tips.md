---
title: "Django quick tips"
date: "2022-10-22"
---

Start a project:
```
poetry new
poetry shell
poetry add Django
django-admin startproject my-project .
```

Create an app:
```shell
python manage.py startapp my-app
```

Run local server:
```shell
python manage.py runserver
```

Migrations:
```shell
python manage.py makemigrations
python manage.py migrate
```

To change your models, you have to `makemigrations`, than `migrate`.

Reset all the mess in migrations:
```shell
find . -path "*/migrations/*.py" -not -name "__init__.py" -delete
find . -path "*/migrations/*.pyc" -delete
rm db.sqlite3
python manage.py makemigrations
python manage.py migrate
```

### Links
- [Cleanest way to get list of Django objects that have same foreign key and display them in a view](https://codereview.stackexchange.com/questions/194906/)