# 2.2 The Web and HTTP
* "HTTP is stateless" = An HTTP server does not remember anything about what happened during earlier steps in interacting with this HTTP client.
* HTTP cookie = A cookie is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this Web browser (**not** person).
* Purpose of HTTP GET = The HTTP GET request message is used by a web client to request a web server to send the requested object from the server to the client.
* Purpose of conditional HTTP GET = To allow a server to only send the requested object to the client if this object has changed since the server last sent this object to the client.

## HTTP response / TCP connection example
Suppose now the server sends the following HTTP response message the client:

HTTP/1.0 200 OK
Date: Wed, 09 Sep 2020 23:46:21 +0000
Server: Apache/2.2.3 (CentOS)
Last-Modified: Wed, 09 Sep 2020 23:51:41 +0000
ETag:17dc6-a5c-bf716880.
Content-Length: 418
Connection: Close
Content-type: image/html

Will the web server close the TCP connection after sending this message?

**Answer:** Yes, the server will close this connection because version 1.0 of HTTP is being used, and TCP connections do not stay open persistently.

## Advantages of web caching
* Caching generally provides for a faster page load time at the client, if the web cache is in the client’s institutional network, because the page is loaded from the nearby cache rather than from the distant server.
* Caching uses less bandwidth coming into an institutional network where the client is located, if the cache is also located in that institutional network.

## HTTP/2 versus HTTP/1.1
* HTTP/2 allows objects in a persistent connection to be sent in a client-specified priority order. 
* HTTP/2 allows a large object to be broken down into smaller pieces, and the transmission of those pieces to be interleaved with transmission of other smaller objects, thus preventing a large object from forcing many smaller objects to wait their turn for transmission.

## What's in an HTTP Reply?
* A response phrase associated with a response code
* A response code

## If-Modified-Since
Purpose of the If-Modified-Since field in HTTP GET request message = To indicate to the server that the client has cached this object from a previous GET, and the time it was cached.

## Cookies
Purpose of cookie value in HTTP GET request = 
The cookie value itself doesn't mean anything. It is just a value that was returned by a web server to this client during an earlier interaction.