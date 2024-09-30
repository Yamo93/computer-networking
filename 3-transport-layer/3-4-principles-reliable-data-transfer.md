# 3.4 Principles of Reliable Data Transfer
## Purposes of Reliable Data Transfer Protocol Mechanisms
**Sequence numbers** = Allows for duplicate detection at receiver.

**ACK** = Lets the sender know that a packet was received correctly at the receiver.

**NAK** = Lets the sender know that a packet was NOT received correctly at the receiver.

**Checksum** = Used by sender or receiver to detect bits flipped during a packet’s transmission.

**Retransmission** = Allows the receiver to eventually receive a packet that was corrupted or lost in an earlier transmission.

## Cumulative ACK
**Q:** What is meant by a cumulative acknowledgment, ACK(n)?

**A:** A cumulative ACK(n) acks all packets with a sequence number up to and including n as being received.

## Stop-and-wait: channel utilization.
**U sender (utilization)** = fraction of time sender busy sending

**Q:** Suppose a packet is 10K bits long, the channel transmission rate connecting a sender and receiver is 10 Mbps, and the round-trip propagation delay is 10 ms.  What is the maximum channel utilization of a stop-and-wait protocol for this channel?

**A:** 0.1.

> 1 Mbps = 1_000_000 bits/sec

> 1 ms (millisecond) = 0.001 sec
```
L = 10_000
L / R = 10_000 / 10 Mbps = 10_000 / 10_000_000 = 1 / 1_000 = 0.001 sec = 1 ms (milliseconds)
RTT = 10ms

U sender = L / R
            _____
            RTT + L / R
         = 1
           _____
           10 + 1
         = 0.09 = 0.1
```

## Channel utilization with pipelining.
**Q:** Suppose a packet is 10K bits long, the channel transmission rate connecting a sender and receiver is 10 Mbps, and the round-trip propagation delay is 10 ms.  What is the channel utilization of a pipelined protocol with an arbitrarily high level of pipelining for this channel?

**A:** 1.0.

**Pipelining** = sender allows multiple, "in-flight", yet-to-be-acknowledged packets.

Consequences of pipelining:
* range of sequence numbers must be increased
* buffering at sender and/or receiver

**Q:** Suppose a packet is 10K bits long, the channel transmission rate connecting a sender and receiver is 10 Mbps, and the round-trip propagation delay is 10 ms.  How many packets can the sender transmit before it starts receiving acknowledgments back?

**A:** 10.

Pipelining means:
* A pipelined sender can have transmitted multiple packets for which the sender has yet to receive an ACK from the receiver. 
* With a pipelined sender, there may be transmitted packets “in flight” – propagating through the channel – packets that the sender has sent but that the receiver has not yet received.

## Packet buffering in Go-Back-N.
**Q:** What are some reasons for discarding received-but- out-of-sequence packets at the receiver in GBN? Indicate one or more of the following statements that are correct.

**A:** 
* The implementation at the receiver is simpler.
* The sender will resend that packet in any case.

---

**Q:** What are some reasons for _not_ discarding received-but- out-of-sequence packets at the receiver in GBN? Indicate one or more of the following statements that are correct.

**A:** Even though that packet will be retransmitted, its next retransmission could be corrupted, so don’t discard a perfectly well-received packet, silly!

---
