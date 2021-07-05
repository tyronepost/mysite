# mysite
Django tutorial site with postgres

### Python Environment Set up

https://github.com/pyenv/pyenv

https://github.com/pyenv/pyenv-virtualenv

### Postgresql setup

Install postgresql using https://brew.sh/
```
$ brew install postgresql
```

To start the database service
```
$ brew services start postgresql
```

To stop the database service
```
$ brew services stop postgresql 
```

### Database setup

To create the database
```
$ createdb mysite
```

Create role `mysite_app`
```
$ pgcli mysite
mysite> CREATE USER mysite_app PASSWORD 'mysite_app'
```

Update the database configuration in ``settings.py``
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'mysite',
        'USER': 'mysite_app',
        'PASSWORD': 'mysite_app',
        'HOST': '127.0.0.1',
        'PORT': '5432',
    }
}
```
