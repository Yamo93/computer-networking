# Socket Programming
## UDP Socket Characteristics
* the application must explicitly specify the IP destination address and port number for each group of bytes written into a socket
* data from different clients can be received on the same socket
* provides unreliable transfer of a groups of bytes (“a datagram”), from client to server
* socket(AF_INET, SOCK_DGRAM) creates this type of socket

## TCP Socket Characteristics
* provides reliable, in-order byte-stream transfer (a “pipe”), from client to server
* socket(AF_INET, SOCK_STREAM) creates this type of socket
* when contacted, the server will create a new server-side socket to communicate with that client
* a server can perform an accept() on this type of socket

## Server Reply (UDP)
**Question**: How does the networked application running on a server know the client IP address and the port number to reply to in response to a received datagram?

**Answer**: The  application code at the server determines client IP address and port # from the initial segment sent by client, and must explicitly specify these values when sending into a socket back to that client.

## How Many Sockets?
**Question**: Suppose a Web server has five ongoing connections that use TCP receiver port 80, and assume there are no other TCP connections (open or being opened or closed) at that server.  How many TCP sockets are in use at this server?

**Answer**: 6

## Socket connect()
**Question**: What happens when a socket connect() procedure is called/invoked?

**Answer**: This procedure creates a new socket at the client, and connects that socket to the specified server.