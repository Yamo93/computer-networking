# 1.4 Performance

## Packet delays
1. Processing delay: time needed to perform an integrity check, lookup packet information in a local table and move the packet from an input link to an output link in a router.
2. Queuing delay: time spend waiting in packet buffers for link transmission.
3. Transmission delay: time spent transmitting packet bits into the link.
4. Propagation delay: time needed for bits to physically propagate through the transmission medium from end one of a link to the other.

> transmission delay = L/R, where L is the packet size, and R is the transmission rate.

## Problem: Transmission delay
Given a packet L = 1500 bytes (1byte=8bits), when link transmits at R = 1Gbps=1,000,000,000 bits per second,
then the transmission delay is:

1500 * 8 = 12 000

L = 12,000 bits

R = 1,000,000,000 bits

L/R = 0.000012 secs

> propagation delay = d/s, where d is the router distance and s is the propagation speed.

## Problem: Propagation delay
Given a link of length 1 000 km, and a propagation speed of 30x10^8 m/sec, then:

d = 1 000 000
s = 300 000 000

d / s = 1 000 000 / 300 000 000 = 1 / 300 = 0.0033s

> throughput = min{RC, RS}

* Throughput = the transmission rate of the bottleneck link.

## Problem: Throughput
Given that all 4 server links are 50 Mbps each, the shared link is 300 Mbps, and all 4 client links are 90 Mbps each, then the maximum throughput is 50.

## Problem: Computing utilization
Given 4 server links with 50 Mbps each, a shared link of 300 Mbps, and 4 client links with 90 Mbps each, then the bottleneck link is: min{RS, R, RC} = min{50, 75, 90} = RS

utilization = bottleneck/link

utilization of server links = RS / RS = 50 / 50 = 1.00

utilization of shared link = RS / R = 50 / 75 = 0.67

utilization of client links = RS / RC = 50 / 90 = 0.56