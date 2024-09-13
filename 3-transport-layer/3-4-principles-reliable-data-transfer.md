# 3.4 Principles of Reliable Data Transfer
## Purposes of Reliable Data Transfer Protocol Mechanisms
**Sequence numbers** = Allows for duplicate detection at receiver.

**ACK** = Lets the sender know that a packet was received correctly at the receiver.

**NAK** = Lets the sender know that a packet was NOT received correctly at the receiver.

**Checksum** = Used by sender or receiver to detect bits flipped during a packet’s transmission.

**Retransmission** = Allows the receiver to eventually receive a packet that was corrupted or lost in an earlier transmission.
