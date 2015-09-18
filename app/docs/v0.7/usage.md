
### Usage:
* in any app's ```models.py``` add
```python
    from djwebsockets.decorator import Namespace
```
* create a websocket handler with a namespace 
```python 
    @Namespace("/example/"):
    class ExamplerHandler:
       @classmethod:
       on_connect(cls, websocket, path):
           ...
       @classmethod:
       on_message(cls, websocket, message):
           ...
       @classmethod:
       on_close(cls, websocket, message):
           ...
```


##### PS:
>There are many more features already present and being made. i'm busy at the moment but documentation will be made soon.
