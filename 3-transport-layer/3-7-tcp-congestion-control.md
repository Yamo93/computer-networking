# 3.7 TCP Congestion Control

## TCP’s AIMD algorithm.
Which of the following statements about TCP’s Additive-increase-multiplicative-decrease (AIMD) algorithm are true?  Check all that are true.

* AIMD cuts the congestion window size,cwnd, i  to 1 whenever a timeout occurs.
* AIMD cuts the congestion window size, cwnd, in half whenever loss is detected by a triple duplicate ACK.
* AIMD is a end-end approach to congestion control.

## TCP’s AIMD algorithm (2).
Q: How is the sending rate typically regulated in a TCP implementation?

A: By keeping a window of size cwnd over the sequence number space, and making sure that no more than cwnd bytes of data are outstanding (i.e, unACKnowledged). The size of cwnd is regulated by AIMD.

## TCP’s Slowstart algorithm.
Q: Which of the following best completes this sentence: "In the absence of loss, TCP slow start increases the sending rate ... "
A: " ... faster than AIMD.  In fact, slowstart increases the sending rate exponentially fast per RTT."

## Uncontrolled transport-layer senders.
Q: Consider the transport-layer flows interacting at a congested link.  In the face of such congestion, what happens at this link to a transport-layer flow that does not cut back on its sending rate?
A: Nothing different from the other flows crossing the congested link.

## TCP CUBIC.
Assuming that the congestion window size,cwnd, has not yet reached Wmax, TCP CUBIC will ...

* ... increase its sending rate faster than AIMD when cwnd is  far away from Wmax, but increase slower than AIMD when cwnd is closer to Wmax
* ... always have a window size, cwnd, and hence a sending rate, higher than that of AIMD (assuming a given window size, Wmax, at which loss would occur).

## Delay-based congestion control. 
 For delay-based congestion control, match the sender action to the relationship  of the currently measured throughput to the value of cwnd/RTTmin
* The currently measured throughput is greater than cwnd/RTTmin = This should never happen.
* The currently measured throughput is equal to or a bit less than than cwnd/RTTmin = increase the sending rate.
* The currently measured throughput is much less that than cwnd/RTTmin = decrease the sending rate.