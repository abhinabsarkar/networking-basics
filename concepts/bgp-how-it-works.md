# BGP - How it works?

BGP is an application layer protocol. Admittedly, most network engineers would wager that it is a network layer protocol – and they would lose that bet!

As an application layer component, BGP leverages Transmission Control Protocol (TCP) for its operations. Specifically, BGP uses TCP port 179. 

BGP uses attributes, and one of the prime attributes of BGP is called the AS Path attribute. This is a list of all of the autonomous systems (AS) that a prefix has had to transit on its journey to, let's say, your autonomous system.

The AS path is effectively a recording of all of this AS path information. The AS path is so critical to the function of BGP, that the protocol is often referred to as a Path Vector routing protocol. Notice this is not a Distance Vector protocol, but a Path Vector. The AS path is not only used to gauge what would be the best path to a destination (i.e. the shorter AS path), it is also used as a loop prevention mechanism.

![alt text](/images/sample-bgp-topology.png)

## Internal And External BGP
If a BGP session is established between two neighbors in different autonomous systems, the session is **External BGP (eBGP)**, and if the session is established between two neighbors in the same AS, the session is **internal BGP**.

Multiple routers usually exist within an AS, so iBGP is necessary whenever BGP advertised information must be passed within a given AS.

## References
* [Fundamentals of BGP](https://www.kwtrain.com/blog/bgp-pt1)
* [BGP Basics: Internal And External BGP](https://www.networkcomputing.com/data-centers/bgp-basics-internal-and-external-bgp)