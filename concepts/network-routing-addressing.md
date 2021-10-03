# Network addressing & routing method
There are four principal addressing methods in the Internet Protocol:
* **Unicast** delivers a message to a single specific node using a <span style="color:green">*one-to-one*</span> association between a sender and destination: each destination address uniquely identifies a single receiver endpoint.
    * [Classes A, B, and C](https://github.com/abhinabsarkar/networking-concepts/blob/master/concepts/subnetting-readme.md#network-classes) provide unicast addresses for networks.
    * Example: 1) Browsing a website. (Webserver is the sender and your computer is the receiver.) 2) Downloading a file from a FTP Server. (FTP Server is the sender and your computer is the receiver).
* **Broadcast** delivers a message to all nodes in the network using a <span style="color:green">*one-to-all*</span> association; a single datagram from one sender is routed to all of the possibly multiple endpoints associated with the broadcast address. The network automatically replicates datagrams as needed to reach all the recipients within the scope of the broadcast, which is generally an entire network subnet. Switches by design will forward the broadcast traffic and Routers by design will drop the broadcast traffic. In other words, Routers will not allow a broadcast from one LAN to cross the Router and reach another Network Segment. The primary function of a Router is to divide a big Broadcast domain to Multiple smaller Broadcast domain.
    * Example: ARP Request message, DHCP DISCOVER Message.
* **Multicast** delivers a message to a group of nodes that have expressed interest in receiving the message using a <span style="color:green">*one-to-many-of-many or many-to-many-of-many*</span> association; datagrams are routed simultaneously in a single transmission to many recipients. Multicast differs from broadcast in that the destination address designates a subset, not necessarily all, of the accessible nodes.
    * Class D has IP address range from 224.0. 0.0 to 239.255. 255.255. Class D is reserved for Multicasting.
    * A common use of multicast is streaming audio, where the audio is published via multicast addressing and clients pick up the routed stream as a channel, Windows Deployment Services (WDS) OS deployment traffic, IP TV etc.
* **Anycast** delivers a message to any one out of a group of nodes, typically the one nearest to the source using a <span style="color:green">*one-to-one-of-many*</span> association where datagrams are routed to any single member of a group of potential receivers that are all identified by the same destination address. The routing algorithm selects the single receiver from the group based on which is the nearest according to some distance measure.
    * Anycast is supported explicitly in IPv6. The same can be done in IPv4, but not as elegantly. [IPv4 vs IPv6](https://www.guru99.com/difference-ipv4-vs-ipv6.html)
    * Anycast routing is widely used by content delivery networks such as web and DNS hosts, to bring their content closer to end users.

![alt text](/images/network-routing.png)

## Anycast - Further detailed
* [What is Anycast?](what-is-anycast.pdf)
* [How Anycast works?](how-anycast-works.pdf)
