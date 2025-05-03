The default gateway for hosts is not 0.0.0.0/0. You're mixing up two related but different concepts:

Default Gateway IP Address: This is the actual IP address of the router interface that connects to the local network. It's a specific address like 192.168.1.1 or 10.0.0.1 that hosts use to send traffic destined for networks other than their own.
Default Route (0.0.0.0/0): This is a routing table entry that represents "all destinations not explicitly listed in the routing table." The notation 0.0.0.0/0 is a route that matches any IP address, essentially saying "if you don't know where to send a packet, send it this way."

In a router's routing table, you might see an entry like:
Destination: 0.0.0.0/0, Next Hop: 203.0.113.1
This means "send all traffic not matching other routes to 203.0.113.1."
For end hosts (computers, phones, etc.), the configuration typically looks like:

IP address: 192.168.1.100
Subnet mask: 255.255.255.0
Default gateway: 192.168.1.1

The host doesn't use 0.0.0.0/0 as its gateway address - it uses the actual IP of the router on the local network.
The confusion might be because the concept of a "default route" (0.0.0.0/0) is related to the function of the default gateway, but they're not the same thing.