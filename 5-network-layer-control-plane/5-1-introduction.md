# 5.1 Introduction to the network layer control plane

## Routing versus forwarding.
Which of the following statements correctly identify the differences between routing and forwarding. Select one or more statements.

- [x] Forwarding refers to moving packets from a router’s input to appropriate router output, and is implemented in the data plane.    
- [ ] Routing refers to determining the route taken by packets from source to destination, and is implemented in the data plane.  
- [ ] Forwarding refers to moving packets from a router’s input to appropriate router output, and is implemented in the control plane.  
- [ ] Routing refers to moving packets from a router’s input to appropriate router output, and is implemented in the data plane.  
- [x] Routing refers to determining the route taken by packets from source to destination, and is implemented in the control plane.  
- [ ] Forwarding refers to determining the route taken by packets from source to destination, and is implemented in the data plane.  
- [ ] Routing refers to moving packets from a router’s input to appropriate router output, and is implemented in the control plane.  
- [ ] Forwarding refers to determining the route taken by packets from source to destination, and is implemented in the control plane.  


## Approaches towards implementing the control plane.
Match the name of the approach towards implementing a control plane with a description of how this approach works.

Per-router control plane = Individual routing algorithm components - with a component operating in each and every router - interact with each  other in the control plane.  The individual routing algorithm component executing in a given router computes the local fowarding table fir that router.

Software-defined networking (SDN) = A (typically) remote controller gathers information from routers, and then computes and installs the forwarding tables in routers.