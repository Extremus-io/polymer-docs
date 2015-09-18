# djwebsockets
The library adds websocket support to django (now any wsgi app). It gives event driven websocket control for simple and straight forward programming.


The idea is to create a separate websocket server when an instance of django wsgi application instance is produced. and kill it as soon as the instance dies.


#### Change-log:
> v0.8.1
> > - Added mixin support
> > - Added ability to run django request middleware on websocket requests through a mixin (see demo chatroom example)
> > - Now works on any WSGI application or desktop application.
> > - Added a demo chatroom example. 

##### Note:
> requires python 3.4 to work
