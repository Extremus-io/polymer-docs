
### Installation:
1. run `pip install djwebsockets`.
1. add ```djwebsockets``` to ```settings.INSTALLED_APPS``` 
1. add ```WEBSOCKET_HOST``` and ```WEBSOCKET_PORT``` to settings.py
1. in wsgi.py file, replace line
```python
    from django.core.wsgi import get_wsgi_application 
```
   with
```python
    from djwebsockets.wsgi import get_wsgi_application
```
1. **optional**: use following for session variables and user (```websocket.user``` and ```websocket.session```)
```python
    WEBSOCKET_MIDDLEWARE = [
        'django.contrib.sessions.middleware.SessionMiddleware',
        'django.contrib.auth.middleware.AuthenticationMiddleware',
    ]
```
