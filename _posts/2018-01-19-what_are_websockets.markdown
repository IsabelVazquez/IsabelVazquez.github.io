---
layout: post
title:      "What are WebSockets?"
date:       2018-01-20 04:11:10 +0000
permalink:  what_are_websockets
---


An interview trend I’ve come across in is being asked about WebSockets. WebSockets is a technology that allows clients/browsers to communicate with servers and vice versa persistently. This differentiates from the traditional paradigm of clients sending requests and servers fulfilling those requests. 

![](http://apress.jensimmons.com/v5/pro-html5-programming/images/ch7/fig7-2.png)

*Image from [apress.jensimmons.com](http://apress.jensimmons.com/)*

As with other [connections](http://isabelcoder.com/2017/09/12/https_in_2017/), a handshake is initiated by the client with a constructor utilizing `ws://` or `wss://` protocol. Once the handshake is complete, data (the payload) is sent without latency costs like traditional HTTP requests. This is because a single HTTP connection is needed and reused for a WebSocket connection. Supported by the browser, pings and pongs are also sent between the server and client to check if the connection is still open.

An immediate, bi-directional connection is best for the following applications:
* interactive games
* collaborative source code editors 
* online chat rooms
* real-time apps with a lot of data and many users 

Once the connection is established, the [WebSockets API](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket) executes the these four different events:
* open - occurs when connection exist
* message - occurs when data is received
* error - self-explanatory
* close - occurs when the connection is closed

and the following methods:
* send - used to send data
* close - used to close the connection

If you’re more curious over other different interactions between clients and servers, read [this StackOverflow answer](https://stackoverflow.com/questions/11077857/what-are-long-polling-websockets-server-sent-events-sse-and-comet) to get started.

Check out [Socket.io](https://socket.io/), a popular WebSocket library.
