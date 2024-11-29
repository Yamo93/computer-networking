# Multiplexing and Demultiplexing
## Transport Layer Demultiplexing
**Transport layer demultiplexing** = Receiving a transport-layer segment from the network layer, extracting the payload (data) and delivering the data to the correct socket.

**Transport layer multiplexing** = Taking data from one socket (one of possibly many sockets), encapsulating a data chunk with header information – thereby creating a transport layer segment – and eventually passing this segment to the network layer.

---

> **True:** When multiple UDP clients send UDP segments to the same destination port number at a receiving host, those segments (from different senders) will always be directed to the same socket at the receiving host.

> **False:** When multiple TCP clients send TCP segments to the same destination port number at a receiving host, those segments (from different senders) will always be directed to the same socket at the receiving host.

> **True:** It is possible for two UDP segments  to be sent from the same socket with source port 5723 at a server to two different clients.

> **True:** It is possible for two TCP segments with source port 80 to be sent by the sending host to different clients.