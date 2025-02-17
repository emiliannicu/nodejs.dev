---
title: build-an-http-server
displayTitle: 'Build an HTTP Server'
description: 'How to build an HTTP server with Node.js'
authors: flaviocopes, potch, MylesBorins, LaRuaNa, ahmadawais, dogafincan
category: learn
---

Here is a sample Hello World HTTP web server:

<iframe
  title="Build an HTTP Server"
  src="https://stackblitz.com/edit/nodejs-dev-0009-01?index.js&zenmode=1"
  alt="nodejs-dev-0009-01 on StackBlitz"
  style="height: 400px; width: 100%; border: 0;">
</iframe>

Let's analyze it briefly. We include the [`http` module](https://nodejs.org/api/http.html).

We use the module to create an HTTP server.

The server is set to listen on the specified port, `3000`. When the server is ready, the `listen` callback function is called.

The callback function we pass is the one that's going to be executed upon every request that comes in. Whenever a new request is received, the [`request` event](https://nodejs.org/api/http.html#http_event_request) is called, providing two objects: a request (an [`http.IncomingMessage`](https://nodejs.org/api/http.html#http_class_http_incomingmessage) object) and a response (an [`http.ServerResponse`](https://nodejs.org/api/http.html#http_class_http_serverresponse) object).

`request` provides the request details. Through it, we access the request headers and request data.

`response` is used to populate the data we're going to return to the client.

In this case with

```js
res.statusCode = 200;
```

we set the statusCode property to 200, to indicate a successful response.

We also set the Content-Type header:

```js
res.setHeader('Content-Type', 'text/html');
```

and we end close the response, adding the content as an argument to `end()`:

```js
res.end('<h1>Hello, World!</h1>');
```
