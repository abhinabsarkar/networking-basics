# DDOS protection: BGP routing vs. DNS routing
DNS routing and BGP routing are two DDoS mitigation techniques that mitigation providers deploy in front of a target network to detect and redirect malicious traffic.

## DNS routing
DNS rerouting involves a mitigation provider masking a target’s IP address as its own. As a result, inbound requests are sent to the mitigation provider, which inspects and filters out any malicious traffic.

A problem with DNS redirection, however, is that it can’t prevent direct-to-origin attacks on an IP address—it only functions at the application layer. This means that even if an IP is masked, it can still be discovered and targeted with malicious traffic.

## BGP routing
BGP rerouting can mitigate direct-to-origin DDoS attacks by screening all incoming network traffic before it reaches its target. It functions at the network level by rerouting malicious network packets to security providers before they can reach DNS servers or other computing resources.

BGP routers can redirect high volumes of traffic to centralized data scrubbing centers used by a security provider. The scrubbing center analyzes traffic and filters out malicious DDoS attack traffic using deep packet inspection. It then allows healthy traffic to pass through to the AS.

## Reference
* [BGP vs DNS routing](https://www.imperva.com/learn/ddos/border-gateway-protocol-bgp/)