> Busy in Exams right now will post updated version later.

- start the `websocket server` when ever you create an instance of wsgi application.
```python
  from djwebsockets.server import WebSocketServer
  
  wserver = WebSocketServer("localhost","8001")
  wserver.start()
```
