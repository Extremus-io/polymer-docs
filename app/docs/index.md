# djwebsockets
The library adds websocket support to django. It gives event driven websocket control for convenience of http programmers.


The idea is to create a separate websocket server when an instance of django wsgi application instance is produced. and kill it as soon as the instance dies.

##### Note:
> Requires python 3.4 to work
