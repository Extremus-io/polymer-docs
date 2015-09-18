### Installation:
- run `pip install djwebsockets`.
- add ```djwebsockets``` to ```settings.INSTALLED_APPS``` 
- add ```WEBSOCKET_HOST``` and ```WEBSOCKET_PORT``` to settings.py
- in `wsgi.py` file, replace line
```python
    from django.core.wsgi import get_wsgi_application 
```
   with
```python
    from djwebsockets.wsgi import get_wsgi_application
```

### Usage:
* in any app's ```models.py``` add
```python
    from djwebsockets.decorator import Namespace
```
* create a websocket handler with a namespace 
```python 
    @Namespace("/example/"):
    class ExamplerHandler:
       @classmethod
       on_connect(cls, websocket, path):
           ...
       @classmethod
       on_message(cls, websocket, message):
           ...
       @classmethod
       on_close(cls, websocket):
           ...
```
* `Namespace` takes a regex expression. if it matches with any websocket connecting, the methods in this class get called.
