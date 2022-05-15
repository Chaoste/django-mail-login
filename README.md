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

### 4. Enable authentication

[Old Source](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Authentication#enabling_authentication)

[Source](https://learndjango.com/tutorials/django-login-and-logout-tutorial)

- Include URLS from `django.contrib.auth.urls`
- Create templates folder and files (e.g. `django.contrib.auth.urls`)
- Configure templates (`DIRS` in `TEMPLATES`)
- Define `LOGIN_REDIRECT_URL`
- Create `templates/home.html` & `templates/base.html`, Update login template
- Add home template to `urls.py`


#### 4.1. Add Admin User
```
$ python manage.py createsuperuser
```

#### 4.2. Test Login & Logout

**Go to [http://127.0.0.1:8000/](http://127.0.0.1:8000/)**

![Home](medium/home-anonymous.png)

**Click on "Log In"**

![Log In](medium/login.png)

**Insert username and password for superadmin**

![Log In](medium/login-success-name.png)

**After logout, try to login with email and password for superadmin**

![Log In](medium/login-fail-mail.png)

### 5. Change Authentication to use Email instead of Username

Initially, create a custom user model: https://docs.djangoproject.com/en/dev/topics/auth/customizing/#using-a-custom-user-model-when-starting-a-project

Followed for model: https://stackoverflow.com/a/43209322

Then add UserManager, etc. like explained in here: https://www.fomfus.com/articles/how-to-use-email-as-username-for-django-authentication-removing-the-username/

Fix translations import like here (for latest Django version): https://forum.djangoproject.com/t/importerror-cannot-import-name-ugettext-lazy-from-django-utils-translation/10943/4


TODO: Give some explanations (see commits in changelog)