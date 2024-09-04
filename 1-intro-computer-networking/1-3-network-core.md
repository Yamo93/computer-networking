# 1.3 The Network Core
Forwarding = the local action of moving arriving packets from router's input link to appropriate router output link.
Routing = the global action of determining the source-destination paths taken by packets.

Packet switching:
* Data may be queued before being transmitted due to other users' data that's also queuing for transmission.
* This technique is used in the Internet.
* Congestion loss and variable end-end delays are possible.
* Resources are used on demand, not reserved in advance.

Circuit switching:
* Reserves resources needed for a call from source to destination.
* Frequency Division Multiplexing (FDM) and Time Division Multiplexing (TDM) are two implementations.
* Was the basis for the telephone call switching from the 20th century and into the beginning of this current century.

### Problem
> Given a circuit-switched network with 4 circuit switches A, B, C and D,
where there are 20 circuits between A and B, 19 circuits between B and C, 15 circuits between C and D, and 16 circuits between D and A, 
then the maximum number of connections that can be ongoing in the network at any one time are: 20 + 19 + 15 + 16 = 70. 

### Definitions of the Internet
* The Internet is made up of access networks at the edge, tier-1 networks at the core, and interconnected regional and content provider networks as well.
* The Internet is made up of a lot of different interconnected networks.

### Packet vs Circuit Switching
Q: 5 users multiplexed over a channel of 10 Mbps. What is better?

Answer:
* Each user generates traffic at an average rate of 2.1 Mbps, generating traffic at a rate of 15 Mbps when transmitting => Neither works well.
* Average rate of 2 Mbps, 2Mbps traffic when transmitting => circuit switching
* Average rate of 0.21 Mbps, 15 Mbps traffic when transmitting => packet switching