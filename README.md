# Django Tutorial - Use Mail for Login

## Setup
[Source](https://docs.djangoproject.com/en/3.2/intro/tutorial01/)

### 1. Install Dependencies
```bash
$ python3 -m pip install virtualenv django
$ python3 -m virtualenv venv
```

### 2. Bootstrap Codebase With Virtualenv
```bash
$ django-admin startproject mysite
$ mv mysite django-mail-login
$ cd django-mail-login
$ virtualenv venv && source venv/bin/activate
(venv) $ pip install django
(venv) $ python -m django --version
> 4.0
```

### 3. Start Server
```
python manage.py migrate
python manage.py runserver
```

Go to [http://127.0.0.1:8000/](http://127.0.0.1:8000/)