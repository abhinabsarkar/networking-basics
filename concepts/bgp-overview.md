# BGP Overview
BGP is the routing protocol of the Internet. BGP is how all Internet routers route your email and web requests across the Internet. Without BGP, no traffic would flow across the Internet and the Internet would be useless. 

<ins>**BGP is our only Exterior Gateway Protocol (EGP) in major use today. Exterior Gateway Protocol (EGP) is a Routing Protocol which is used to find network path information between different networks. It is commonly used in the Internet to exchange routing table information between two neighbor gateway hosts (each with its own router) in a network of autonomous systems.**</ins>

> Link to [autonomous system (AS)](https://en.wikipedia.org/wiki/Autonomous_system_(Internet))

## BGP history
In the early days, the Internet used static routes as there were only a few networks connected to each other. But very quickly network administrators couldn’t keep manually updating their routing tables as internet stated to grow. Later, Internet network admin’s used a protocol called EGP (External Gateway Protocol). EGP is a simple routing protocol and, consistent with the period it was created in, is based on tree-like (i.e., hierarchical) topologies. In modern networks, tree topologies were replaced by fully connected mesh topologies to allow for maximum scalability.

![alt text](/images/tree-vs-mesh.png)

As the Internet continued to expand, it became increasingly difficult to keep track of all the routes from one network to another. The solution was to transition to an Autonomous System (AS) architecture.

An AS can be an Internet Service Provider, a university or an entire corporate network, including multiple locations (IP addresses). Each AS is represented by a unique number called an ASN.

In this type of network architecture, each autonomous system controls a collection of connected routing prefixes, representing a range of IP addresses. It then determines the routing policy inside the network.

As the number of autonomous systems in the internet grew, the drawbacks of EGP became more pronounced. Its hierarchical structure hampered scalability and made it difficult to connect new networks in an efficient manner. Consequently, it was necessary to define a new exterior routing protocol that would provide enhanced and more scalable capabilities.

In June 1989, the first version of this new routing protocol, known as the Border Gateway Protocol, was formalized.

## BGP is Just Like GPS for Packets
Let’s draw an analogy from everyday life to make all of this a bit more understandable.

You can think of an autonomous system in the computer world as a city with many streets. A network prefix is similar to one street with many houses. An IP address is like an address for a particular house in the real world, while a packet is the equivalent of a car travelling from one house to another using the best possible route.

Taking this comparison to its logical conclusion, the BGP routing protocol is analogous to your trusty GPS navigator. Like Google’s Waze application, the best route is determined by different factors, such as traffic congestion, roads temporarily closed for maintenance, etc. The path is calculated dynamically depending on the situation of the network nodes, which are like roads and junctions on a GPS map.

## BGP in technical terms
BGP4 is based on RFC4271. BGP is a routing protocol (software) that runs on routers. BGP allows for fully decentralized management of the Internet. That means, if you have a BGP router on the Internet, you can tell all other routers what networks you have available to everyone in the world.

<ins>**BGP calls each routing domain an autonomous system (AS). BGP is called a path vector routing protocol and its main metric is “shortest AS path”. That means that it selects the best path, through the Internet, by choosing the route that has to traverse the fewest autonomous systems.**</ins>

## Do I need to run BGP on my home or small business router?
The short answer to this question is NO. You do not need to run BGP on your home or small business router. All Internet Service Providers (ISPs) that have multiple connections to the Internet use BGP to communicate with those other providers. If you only have a single connection to the Internet, you don’t need BGP because you don’t have any other path to select from. Because of that, you don’t need a routing protocol to select the best path.

## What if I want to run BGP?
If you want to run BGP, you will have to talk to your Internet Service Providers to see if they will agree to communicate with you via BGP. You will have to show your need to run BGP. There are no cable or DSL internet providers that will allow you to communicate with them via BGP. The only circuits that you will be using BGP on are [T1 speeds](https://oneringnetworks.com/what-is-a-t1-line-and-how-fast-is-t1-internet/) (1.544 Mbps) and above. The only providers that will allow you to exchange BGP routes with them are major (Tier 1 or Tier 2) Internet Service Providers.

Let’s say that you have a T1 to Sprint and a T1 to AT&T. To run BGP, you will have to obtain an autonomous system number and block of public IP addresses to advertise. In the United States, both of these can be obtained from the American Registry of Internet Numbers (ARIN). Other countries have their own providers. You can find yours through the ARIN International Community webpage. These regional registries (like ARIN) are also places to turn to, to troubleshoot networking by looking up the owners and contact information for IP address blocks and AS numbers. There are BGP looking glass servers on the Internet that you can use to view the status and BGP routing tables of Internet BGP routers.

With BGP, your router will download a full list of Internet routes from your ISPs (BGP neighbors). A full list of Internet BGP routes is over 150,000 routes. That means, with two providers, you will have to download over 300,000 routes. Your router will put all those routes into memory and compare them to find the best route (the route with the shortest AS path). The best routes will be put into the routing table. As you might guess, you will need a strong router with a fast CPU and lots of RAM to process these BGP routes. I recommend at least a Cisco 3800 series router with 1GB of RAM.

## References
* [What is BGP](https://petri.com/csc_what_is_bgp)
* [BGP routing explained](https://www.imperva.com/blog/bgp-routing-explained/)
* [Fundamentals of BGP](https://www.kwtrain.com/blog/bgp-pt1)