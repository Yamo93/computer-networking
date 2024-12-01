# Network Layer Overview

## The network layer - where is it? 

- [x] The network layer is implemented in hosts at the network's edge.

- [x] The network layer is implemented in routers in the network core.


## Forwarding versus routing.
Consider the travel analogy discussed in the textbook - some actions we take on a trip correspond to forwarding and other actions we take on a trip correspond to routing.  Which of the following travel actions below correspond to forwarding? The other travel actions that you don't select below then correspond to routing.  

(x) A car takes the 3rd exit from a roundabout.

(x) A car waits at light and then turns left at the intersection.

(x) A car stops at an intersection to “gas-up” and take a “bathroom break”

## The control plane versus the data plane.
For each of the actions below, select those actions below that are primarily in the network-layer data plane. The other actions that you don't select below then correspond to control-plane actions.  

(x) Moving an arriving datagram from a router’s input port to output port

(x) Dropping a datagram due to a congested (full) output buffer.

(x) Looking up address bits in an arriving datagram header in the forwarding table.

## What type of control plane?
We've seen that there are two approaches towards implementing the network control plane - a per-router control-plane approach and a software-defined networking (SDN) control-plane approach.  Which of the following actions occur in a per-router control-plane approach? The other actions that you don't select below then correspond to actions in an SDN control plane.  

- [x] A router exchanges messages with another router, indicating the cost for it (the sending router) to reach a destination host.

- [ ] All routers in the network send information about their incoming and outgoing links to a logically centralized controller.
- [x] Routers send information about their incoming and outgoing links to other routers in the network.
- [ ] A control agent in router receives a complete forwarding table, which it installs and uses to locally control datagram forwarding.

