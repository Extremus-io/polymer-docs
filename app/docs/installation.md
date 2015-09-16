
### Installation:
1. Run `pip install djwebsockets`.
1. Add ```djwebsockets``` to ```settings.INSTALLED_APPS``` 
1. Add ```WEBSOCKET_HOST``` and ```WEBSOCKET_PORT``` to settings.py
1. In wsgi.py file, replace line
```python
    from django.core.wsgi import get_wsgi_application 
```
   with
```python
    from djwebsockets.wsgi import get_wsgi_application
```
1. **optional**: Use following for session variables and user (```websocket.user``` and ```websocket.session```)
```python
    WEBSOCKET_MIDDLEWARE = [
        'django.contrib.sessions.middleware.SessionMiddleware',
        'django.contrib.auth.middleware.AuthenticationMiddleware',
    ]
```
