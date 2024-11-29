# 3.8 Evolution of Transport Layer Functionality

## QUIC streams.
What are advantages of the streams concept in QUIC? Select all that apply.

* Since each stream has its own error control, if one stream experiences an error (e.g., lost or damaged segment), the other streams are unaffected.
* Streams allow concurrent retrieval of web objects, while avoiding Head of the Line (HOL) blocking.

## QUIC: an application-layer protocol.
What are advantages of implementing transport-layer functionality in QUIC at the application layer? Select all that apply.
* QUIC can establish all connection parameters (security, reliability, flow and congestion control)in just one handshake rather than separately in two.
* As an application-layer protocol, QUIC can be updated/modified at “app frequency” rather than at the frequency of operating system updates.