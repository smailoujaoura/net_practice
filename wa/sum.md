# Get to know the words: dhcp, www, http, router...
- Data Communications and Networking Ferzan.

- Network:
	- A network is two any devices(node, host, client, server) connected with each other.
	- A network is composed of: 
		- message(data), 
		- client, server. This is a client-server model. There are others.
		- There is also the medium called medium media.
		- There is hardware and software: protocols that ensure conformance, router, switch
		- ![alt text](image.png)


## Data Flow Types/ Data Transimission Types/ Types of Networks
- Simplex (one way), keyboard, mouse, monitor, etc. The data flows in one way.
- Half-duplex: (two way but not concurrently) walkie-talkie, "Cut" "Roger"
- Full-duplex: (two way concurrently) phones.
![alt text](image-1.png)

- point-to-point connection topology: node connects to one node and does not share means of transmission with other nodes.
- multi-point topology: shares means of transmission with other nodes.
- which one is better and efficient


- unicast: data goes from node to router to a single node
- broadcast: (like radio statios get the message all) data goes from one node to all in the network 
- multicast: data goes from one node to multiple but not all nodes
- how to do each relates to ip addressing etc.

- Scale of Networks:
	- PAN: personal area network, bluetooth device connected to computer, RFID, wireless, 1m-10m
	- LAN: local area network, at the level or scale of house, building, enterprise network, etc.: 10m-100m, peer-to-peer
		- VLAN: this helps in dividing the networks logically and physically, switches, etc. depeding on organization departements
		- WiFi used here.
	- MAN: Metropoletean Area Network: at the scale of cities 
		- WiMax; can span 10s of kilometers
![alt text](image-2.png)
	- WAN: Internet as an example, Wide Area Network, can connect with sattelite, fiberoptics through intercontinetal,
		- VPN: virtual private network: there is a company that is multi-national, how can we connect the two networks?
			- It is a technique that allows making LAN (private network) inside a public network WAN. Data goes through Internet. 
				- Achieved mainly with cryptography.

- internet vs Internet:
	- internet means internetwork and not necessarily what we use every day, apps and websites. Internet is what we use. 
![alt text](image-4.png)

# Network Topology/ (Mesh, star, bus, ring)
- it is the way we connect the nodes or the networks layout, and there are 4 main ways: Mesh, star, bus, ring
	- Mesh: every node is connected seperately to each other node. If we have 5 nodes then we would have 4 connections from each node. point to point in each node.
		- requiring n(n-1) links. 5(5-1) = 20; 3(3-1)=6
		- robust, does not affect links between other nodes if one link goes down.
		- secure, no third party or shared points
		- costs more, harder configuration, 
	- Star: very widely used, you have a hub in the middle that connects many other nodes.
		- less cabling, costs less, easier config, robust too
		- dependent on one node that might go down
		- more cabling than bus and ring
	- Bus: was used a lot early with ethernet networks. There is a backbone cable and each node takes from that central cable
		- easy to install, lesser cabling, single point of failure(backbone), less secure, difficult fault isolation
	- Ring: nodes are like dining philosophers, repeater needed to amplify signals when they crumble 
		- easy to install and reconfigure, lesser cabling
		- dependent on single link, this is solved with dual-ring.


# Networks/ circuit-switched networks/ packet-switched networks
- We first start with hardware components of a networks, types of networks, topologies, then we will dive into the software components.

- Circuit-switched networks: There is a a dedicated connection called ciruit for each connection in the switch, analog signals connection
- Packed-switched networks: packet will be talked about when talking about OSI and layers.
	- there is no dedicated link. The packets reaches a ROUTER(most important device in networks) gets it and forwards it. gotten in a queue and forwared
	- store-and-forward.
![alt text](image-3.png)


# Networks/ Network Software/ Protocol Stack/ Layers
- The software part is what matters to us as software developers.
- When you connect two nodes with hardware you have not made a network as it is not configured, no communication
- The networks differ very much so there must be a standard that all technologies:Operating systems, devices, etc. conforms to.
- Protocol: a bunch of rules that are agreed upon by all parties.
- Protocol suite, protocol stack: there are many protocols and each does it's job. FTP, HTTP, IP, TCP, a bunch of algos and rules and languages
- In Network software: there is protocol hierarchies.
- The protocols stack/suite should be in all nodes in the network = I can connect the two
![alt text](image-5.png)
![alt text](image-6.png)
- OSI model	7layers, more academic
- TCP/IP	4layers, was developed following rules from OSI, same nearly.
- The reasons there is layers is because for easy design and engineering. 
- Each layer provides services to higher layer.
![alt text](image-7.png)
- Encapsulation: the message will be encapsulated with headers or footers(tailers) at each layer.
![alt text](image-8.png)
- Design Issues for the layers:
	- Addressing, which one to send to.
	- Error control, noise detection and correcting achieved with tailer(footer in some layer)
	- Flow control, flow of data how to control it
	- Multiplexing, sharing the signal
	- Routing, which port to send data to,


# Data Communication Units
- for 1600*1200 pixels image with 3bytes/pixel, uncompressed. How long to transmit through
	- 56-Kbps modem channel
	- 1-Mbps cable modem
	- 10-Mbps Ethernet
	- 100-Mbps gigabit Ethernet
- In storage:
	- b, B, MB, GB, powers of two.
- In communication:
	- Kbps = 1000 bit / sec
	- Mbps = 1000 Kbps = 1,000,000 b
- Bit = 1
- Byte = 8 bits
- Kilo Byte = 2^10(power of two because machines are binary) 1024 Byte
- MegaByte = 2^10 1024 KB
- GB = 2^10 MB

- 1 920 000 pixel * 3 Bytes/pixel =  5 760 000 Bytes * 8 bits / Byte = 46 080 000 bit / 56000 bits / 1s = 46 080 000 bit * 1s / 56000 bits = 
	= 823 seconds with modem 56-Kbps = 14 mins
- same way of calculation you can use dimentional analysis tricks from chemistry to not confuse onself.

# OSI Model / TCP-IP Model
- the software needs to be controlled by software which is divided into modules or layers:
- these are the two most known ones, and the one used now is TCP-IP, OSI is academic and divides layers further and easy to understand comparbly with TCP-IP and has more details.
![alt text](image-9.png)
- Some say TCP-IP is 4 layers other say it is 5 layers, but official TCP-IP is 4 layers the other with 5 layers is used in some courses and academia to match OSI more closely, seperating physical and data link layers
![alt text](image-10.png)
![alt text](image-11.png)
- OSI:
	- APPLICATION: TELNET, SSH, FTP, SMTP, DNS
	- TRANSPORT: TCP 	UDP
	- NETWORK:	IP
	- PHYSICAL+DATA LINK:	ARPANET SATNET PacketRadio LAN
- These layers have many protocols for each and each protocol has its own use and usage.
- Each layer must be able to perform the action it does and de-perform it, or perform it in reverse.
- The data must be the same at each layer opposite sides
- It was named TCP/IP layer 4, layer 3 for these two layers are the most famous.
![alt text](image-12.png)
- Connection-oriented => TCP => has to make a logical connection before sending data, connected, aknowledgement
- Connection-less => UDP, just sends without checking, low-overhead, SPAM EMAILS, UDP diagram TCP segment
	- There are some other differences: TCP has these three
		- flow control: controls flow, buffer controlling, can control how many 
		- error control: finds error in some segments and would fix it wit different algorithms.
		- congestion control:



# Network Layer / Logical Addressing
- logical address:
	- called logical because it is controlled by a software and assigned by it. physical address is printed in the NIC
	- 32 bit, +4billions device
	- unique and universal.
	- hierarchical addressing system
		- network and host
		- subnetting: network, host, subnet(mask)
	- As the Internet boomed the 4 billions ips was no longer sufficient so they come up with ways to fix the issue:
	- Octet Octet Octet Octet or dotted decimal notation. 
	- 0-255, so we have 256 options.
	- The reason there is a hierarchical division(network portion, host portion) is to make the routing efficient for the router using the routing table because there are many portals the router handles
- Classful Addressing: makes routing easier for router as it only has to look at the first bits of the first bytes
	- Class A: 0	0-127.max() how many networks would be in class A with CIDR 8 = 254 because there is 8 bits in the network portion which means 2^8 - 2
	- Class B: 10	128-191
	- Class C: 110	192-223
	- Class D: 1110 multi casting purposes
	- Class E: 1111 research purposes
![alt text](image-13.png)
- with each class a number of bits stay as is. 0, 10, 110, 1110, etc.
![alt text](image-14.png)
- Private addresses:
![alt text](image-15.png)
![alt text](image-16.png)
- the host address which basically means the newly non given ip address which DHCP will give them ip address if they had this 0.0.0.0 or any other host address

# Classful addressing / default masks NO SUBNETTING
- In classful addressing we need masks, I also need the class of the ip
- no subnetting = classfull
- subnetting = class-less
- they both have a mask but in classful it is called default mask, in class-less(subnetting) the mask is called subnet mask.
- What is the use of the mask, it basically tells us how big the network portion is, and host portion
![alt text](image-17.png)
- what is a network address, the first ip of the network? basically what the router uses to route the packet to another router that has that network address
![alt text](image-18.png)
- broadcast ip: sometimes the router wants to send messages to all nodes in the networks so he uses the braodcast ip the last ip, not necessarily ends in .255 ? in the case of 192.168.1.64 / 26 network: 192.168.1.64; broadcast: 192.168.1.127
![alt text](image-19.png)
- Find the first and last ip addresses for the IP address: 9.16.37.39/8 
	- you can convert first octet to binary to see which class is this. 00001001 so it is class A, can also look at the CIDR which tells us class A becuase class A has 255.0.0.0 8 bits of networks
	- 9.0.0.0 is the first address in the network. because we set the right most 32 - n bits to 0. n = CIDR = number of bits in network portion
	- the last IP: setting the right most 32 - n bits to 1: 9.255.255.255 
	- the number of ip addresses available in the network: 2^(32 - n) => 2^(32 - 8) = 2^24 = 16 777 216, 
	- there is no company that has 16 million devices so this method is really wasteful so there comes subnetting.
	- first ip: mask in binary AND ip = first ip, anding is very fast in processors
	- last ip: ~mask in binary(complemented) OR ip = last ip.
- Bitwise operations will be very useful for classless addressing those ip won't take form from the beginning. 
- 130.50.3.5/16 class B
	- 130.50.0.0
	- 130.50.255.255
	- 65 536


# Classless Addressing / Subnetting / Subnet Masks
- Classful addressing became obselete for its wastefulness
- The Internet authroities impose three restrictions on classless address blocks:
	1- The addresses in a block must be contiguous
	2- The number of addresses in a block must be a power of 2
	3- The first address must be evenly divisible by the number of addresses
		- first ip address / number of addresses in bloc = 2n; n is a natural number.
![alt text](image-20.png)
- There is also a VLSM way to avoid theses losses:
	- a company requests 120 ips addresses, we give them 128, there is a waste of 8 ips. Variable Length Subnet Mask
![alt text](image-21.png)
![alt text](image-22.png)
![alt text](image-23.png)
- Subnetting
	- Good for easy management and control 
	- network traffic reduced which improves performance
	- more easily apply security policises
	- minimized waste in IP addresses
![alt text](image-24.png)
![alt text](image-25.png)
![alt text](image-26.png)
![alt text](image-27.png)
![alt text](image-28.png)
![alt text](image-29.png)
![alt text](image-30.png)
![alt text](image-31.png)
![alt text](image-32.png)
![alt text](image-33.png)
- VLSM will give us variable numbers of hosts unlinke classless which divides a network into equal subnets.
- Here each subnet mask differs, sort from the biggest hosts needs
- we keep n bits for hosts the amount 2^n >= hosts
![alt text](image-34.png)
![alt text](image-35.png)
![alt text](image-36.png)
![alt text](image-37.png)
- how?
![alt text](image-38.png)
![alt text](image-39.png)
![alt text](image-40.png)
![alt text](image-41.png)
- Network layer or Internet layer in TCP/IP: IPv4, Internet Protocol in TCP is at this layer 2, logical addres vs physical addressing(mac in NIC)
- IP how does it do logical addressing: give packets headers so that it goes to the right place