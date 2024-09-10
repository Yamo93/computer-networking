# Introduction and Transport Layer Services
## Location of Transport Layer Functionality
**Q:** Where is transport-layer functionality primarily implemented?

**A:** Transport layer functions are implemented primarily at the hosts at the “edge” of the network.

---

> **Fact:** The transport layer provides for host-to-host delivery service.

## Transport Layer Services Using TCP
* In-order data delivery
* A byte stream abstraction, that does not preserve boundaries between message data sent in different socket send calls at the sender.
* Reliable data delivery.
* A flow-control service that ensures that a sender will not send at such a high rate so as to overflow receiving host buffers.
* A congestion control service to ensure that multiple senders do not overload network links.

## Transport Layer Services Using UDP
* A message abstraction, that preserves boundaries between message data sent in different socket send calls at the sender.

## Network Layer Functionality

> The transport layer sits on top of the network layer, and provides its services using the services provided to it by the network layer.  Thus it’s important that we know what is meant by the network layer’s “best effort” delivery service. 

> The network layer’s best-effort delivery service means that IP makes its “best effort” to deliver segments between communicating hosts, but it makes no guarantees. In particular, it does not guarantee segment delivery, it does not guarantee orderly delivery of segments, and it does not guarantee the integrity of the data in the segments.