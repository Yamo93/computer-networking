# DNS
## DNS Functions
* Authoritative DNS server = Provides authoritative hostname to IP mappings for organization's named hosts.
* Local DNS server = Replies to DNS query by local host, by contacting other DNS servers to answer the query.
* Top Level Domain (TLD) servers = Responsible for a domain (e.g. *.com, *.edu); knows how to contact authoritative name servers.
* DNS root servers = Highest level of the DNS hierarchy, knows how to reach servers responsible for a given domain (e.g. *com, *.edu).

---

```
DNS root servers
        |
        \/
Top Level Domain (TLD) servers
        |
        \/
Authoritative DNS server
```

---

> A local DNS server does not strictly belong to the hierarchy of DNS servers, but is nevertheless central to the DNS architecture.

---

## Value of Caching in the Local DNS Name Server
* DNS caching provides for faster replies, if the reply to the query is found in the cache.
* DNS caching results in less load elsewhere in DNS, if the reply to a query is found in the local cache.

## Resource Records in the DNS Database
* Type "A" = A hostname and an IP address.
* TODO: add types

## Problem:
Given the following DNS architecture:
```
local host
    |
local DNS server
    |
root - TLS - authoritative
```

And the following assumptions:
> Suppose that the local DNS server caches all information coming in from all root, TLD, and authoritative DNS servers for 20 time units. (Thus, for example, when a root server returns the name and address of a TLD server for .com, the cache remembers that this is the TLD server to use to resolve a .com name).  Assume also that the local cache is initially empty, that iterative DNS queries are always used, that DNS requests are just for name-to-IP-address translation, that 1 time unit is needed for each server-to-server or host-to-server (one way) request or response, and that there is only one authoritative name server (each) for any .edu or .com domain.

And the following DNS requests:
* t=0, the local host requests that the name gaia.cs.umass.edu be resolved to an IP address. 
* t=1, the local host requests that the name icann.org be resolved to an IP address. 
* t=5, the local host requests that the name cs.umd.edu be resolved to an IP address. (Hint: be careful!)
* t=10, the local host again requests that the name gaia.cs.umass.edu be resolved to an IP address. 
* t=12, the local host requests that the name cs.mit.edu be resolved to an IP address. 
* t=30, the local host **again** requests that the name gaia.cs.umass.edu be resolved to an IP address. (Hint: be careful!)

**Then**: 

* the requests t=0, t=1 and t=30 require 8 time units to be resolved,
* the requests t=5 and t=12 require 6 time units to be resolved,
* and the request t=10 requires 2 time units to be resolved.

t=0 : localhost>local_DNS>root>local_DNS>TLD>local_DNS>auth>local_DNS>localhost = 8 edges

t=1 : localhost>local_DNS>root>local_DNS>TLD>local_DNS>auth>local_DNS>localhost = 8 edges

t=30 : localhost>local_DNS>root>local_DNS>TLD>local_DNS>auth>local_DNS>localhost = 8 edges = because the cache is cleared after 20 time units.

t=5 : localhost>local_DNS>TLD>local_DNS>auth>local_DNS>localhost = 6 edges

t=12 : localhost>local_DNS>TLD>local_DNS>auth>local_DNS>localhost = 6 edges

t=10 : localhost>local_DNS>localhost = 2 edges

## Local DNS Server Characteristics
* The local DNS server can decrease the name-to-IP-address resolution time experienced by a querying local host over the case when a DNS is resolved via querying into the DNS hierarchy.
* The local DNS server record for a remote host is sometimes different from that of the authoritative server for that host.

## DNS Authoritative Name Server Characteristics
* It provides the definitive answer to the query with respect to a name in the authoritative name server's domain.

## DNS and HTTP Caching
**Question:** In which of the following forms of caching does a user benefit from its not only from its own recent requests (and cached replies) but also from recent requests made from other users?

**Answer**: 

[x] Local DNS server caching

[x] HTTP local web caching

[ ] HTTP browser caching.