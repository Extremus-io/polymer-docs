
### Mixins:
- mixins essentially process all or some of the events before actual handler, allowing to tweak the data or block the event call.
- creating mixin is a lot similar to creating the handler itself. 
```python
    class ExampleMixin(BaseMixin):
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
- The mixin has to extend `djwebsockets.mixins.BaseMixin` class
- To use this mixin in your app, extend your handler with this mixin
```python 
    @Namespace("/example/"):
    class ExamplerHandler(ExampleMixin):
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
- You can also add multiple mixins. They will be executed from right to left.
```python 
    @Namespace("/example/"):
    class ExamplerHandler(ExampleMixin1 ,ExampleMixin2, ExampleMixin3):
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

### \*\*Experimental\*\* django middleware support:

- Django middleware can be used to authentication, sessions etc. (```websocket.user``` and ```websocket.session```)
- To activate django middleware, extend your websocket handler with `djwebsockets.mixins.wsgi.WSGIMixin`.
- add middle you want to run just like django.
```python
    WEBSOCKET_MIDDLEWARE = [
        'django.contrib.sessions.middleware.SessionMiddleware',
        'django.contrib.auth.middleware.AuthenticationMiddleware',
        'django.contrib.auth.middleware.SessionAuthenticationMiddleware',
    ]
```
> For general Auth, session the above three or their equivalents will be sufficient.
