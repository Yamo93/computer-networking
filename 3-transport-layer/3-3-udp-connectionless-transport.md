# UDP - Connectionless Transport

> **True:** On the sending side, the UDP sender will take each application-layer chunk of data written into a UDP socket and send it in a distinct UDP datagram. And then on the receiving side, UDP will deliver a segment’s payload into the appropriate socket, preserving the application-defined message boundary.

## UDP Header Fields
* Internet checksum
* Source port number
* Destination port number
* Length (of UDP header plus payload)

## UDP Segment Length Field
**Q:** Why is the UDP header length field needed?

**A:** Because the payload section can be of variable length, and this lets UDP know where the segment ends.

## Internet Checksum and UDP
**Q:** Over what set of bytes is the checksum field in the UDP header computed over?
**A:** The entire UDP segment, except the checksum field itself, and the IP sender and receive address fields

## Checksum Characteristics
* A checksum is computed at a sender by considering each byte within a packet as a number, and then adding these numbers (each number representing a bytes) together to compute a sum (which is known as a checksum).
* The sender-computed checksum value is often included in a checksum field within a packet header.
* The receiver of a packet with a checksum field will add up the received bytes, just as the sender did, and compare this locally-computed checksum with the checksum value in the packet header. If these two values are _different_ then the receiver _knows_ that one of the bits in the received packet has been changed during transmission from sender to receiver.

## Computing the Internet Checksum
Recall the following rules for binary addition:

| Input | Output             |
|-------|--------------------|
| 0+0   | 0                  |
| 1+0   | 1                  |
| 1+1   | 0, with carry of 1 |
| 1+1+1 | 1, with carry of 1 |

### Problem:
Given these two 16-bit words:

`11110101 11010011` and `10110011 01000100`,

Then the Internet checksum value is `01010110 11100111`.

### 1. Add both words: 
Add both words:
```
 11110101 11010011
 10110011 01000100
 _________________
110101001 00010111
```

### 2. If any overflow, wrap around
There is an overflow of 1, so we "wrap around", i.e. add 1 to the sum:
```
 10101001 00010111
 00000000 00000001
 _________________
 10101001 00011000
```

### 3. Invert the sum to get the checksum
Then, we compute the checksum by inverting the sum:
```
 01010110 11100111
```
