# 2.1 Principles of Network Applications
## Characteristics of the Client-Server Approach
* HTTP uses this application structure.
* There is a server with a well known server IP address.
* There is a server that is always on.

## Characteristics of the P2P Approach
* There is _not_ a server that is always on.
* A process requests service from those it contacts and will provide service to processes that contact it.

## UDP Service
* Best effort service.  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.

## TCP Service
* Loss-free data transfer. The service will reliably transfer all data to the receiver, recovering from packets dropped in the network due to router buffer overflow.
* Flow Control. The provided service will ensure that the sender does not send so fast as to overflow receiver buffers.
* Congestion control.  The service will control senders so that the senders do not collectively send more data than links in the network can handle.