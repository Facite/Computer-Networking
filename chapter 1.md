# Chapter 1: Computer Networks and the Internet

## Index

###### 1.1 [What is the Internet?](#11-what-is-internet)

###### 1.2 [Network Edge](#12-the-network-edge)
+ 1.2.1 [Access Networks](#121-access-networks)
+ 1.2.2 [Physical Media](#122-physical-media)

###### 1.3 [Network Core](#13-the-network-core)
+ 1.3.1 [Packet Switching](#131-packet-switching)
+ 1.3.2 [Circuit Switching](#132-circuit-switching)
+ 1.3.3 [A Network of Networks](#133-a-network-of-networks)

###### 1.4 [Delay, Loss, and Throughput in Packet Switched Network](#14-delay-loss-and-throughput-in-packet-switched-networks)
+ 1.4.1 [Overview of Delay](#141-overview-of-delay-in-packet-switched-networks)
+ 1.4.2 [Queuing Delays and Packet Loss](#142-queuing-delays-and-packet-loss)
+ 1.4.3 [End-system Delays](#143-endsystem-delays)
+ 1.4.4 [Throughput in Computer Networks](#144-throughput-in-computer-networks)

###### 1.5 [Protocol Layers and their Service Model](#15-protocol-layers-and-their-service-models)
+ 1.5.1 [Layered Architecture](#151-layered-architecture)
+ 1.5.2 [Encapsulation](#152-encapsulation)

###### 1.6 [Networks Under Attacks](#16-networks-under-attack)
+ 1.6.1 [Malware](#161-malware)
+ 1.6.2 [Denial of Service](#162-denial-of-service-dos)
+ 1.6.3 [Packet Sniffing](#163-packet-sniffing)
+ 1.6.4 [IP Spoofing](#164-ip-spoofing)
+ 1.6.5 [Why is the Internet so Insecure?](#165-why-is-internet-so-insecure)

###### 1.7 [The History of Computer Networking and the Internet](#17-history-of-computer-networking-and-the-internet)
+ 1.7.1 [The Development of Packet Switching](#171-the-development-of-packet-switching-1961-72)
+ 1.7.2 [Proprietary Networks and Internetworking](#172-proprietary-networks-and-internetworking-19721980)
+ 1.7.3 [A Proliferation of Networks](#173-a-proliferation-of-networks-19801990)
+ 1.7.4 [The Internet Explosion](#174-the-internet-explosion-the-1990s)
+ 1.7.5 [The New Millenium](#175-the-new-millennium)


___

### 1.1 What is Internet?

##### The Internet
+ Can be thought of as a computer network that interconnects billions of computing devices around the globe.
+ It can also be thought of as an infrastructure that provides services to applications.
	+ End systems attached to the Internet connect to it via a "socket interface". 
	+ This Internet socket interface specifies how a program running on one end system can ask the 'Internet infrastructure' to deliver data to a specific destination program running on another end system.

##### End Systems 
+ Segment the data they want to send and add headers to the segments (making them "packets").  
+ Send the packets through network to the destination (where they are reassembled into the original data).
+ Access the internet using ISPs (Internet Service Providers)
+ Are also referred to as hosts
+ Are sometimes further categorised into two categories - server or client.

##### Packet Switches
+ Are devices such as routers and link layer switches
+ Take a packet arriving to one of its incoming communication links
+ Forwards the packet through one of its outgoing communication links (with the help of its destination address)  

##### Internet Standards 
+ To connect devices across the globe, we need common standards.
+ Internet standards are developed by the Internet Engineering Task Force (IETF)
+ Their standard documents that detail protocols are called Requests for Comments (RFCs)
+ The IEEE 802 LAN/MAN Standards Committee specifies the Ethernet and wireless WiFi standards.

##### Network Protocols 
+ All activities on the internet involving two or more interconnected remote entities are governed by a protocol.
+ A protocol defines the format and the order of messages exchanged between communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.
+ Mastering the field of computer networking is equivalent to understanding the what, why, and how of networking protocols.

___

### 1.2 The Network Edge

#### 1.2.1 Access Networks
+ Access network is the network that connects an endsystem to its ISP. 
+ Some of the most popular broadband residential access are: 
	+ Digital subscriber line - telco uses the existing telephone line (twisted pair copper wire) and DSL modem to provide internet access to customer.
	+ Cable internet access - cable provider uses the existing cable line (coaxial cable) and cable modem to provide internet access to customer. 
	+ Fiber to the home (FTTH) - internet provider provides fiber cable and optical network terminator (ONT) to provide internet access to customer.
	+ Satellite link
	+ Dial up connection - using telephone infrastructure (similar to DSL, but way slower).
+ For connecting the device to the internet, most popular methods are:
	+ Ethernet cable (twisted pair copper wire) \[Wired LAN\] 
	+ WiFi (IEEE 802.11) \[Wireless LAN\]
	+ 3G, 4G (LTE) \[Wireless WAN\]

#     
<!--Empty Heading--> 

#### 1.2.2 Physical Media
+ It is the transmission mediums through which the bit travels.
+ Can be categoriesed into two categories:
	+ Guided media (solid medium)
	+ Unguided media (atmosphere and outer space)

##### Guided Media
+ Twisted pair copper wire
	+ Least expensive, most commonly used. Data rate for LAN using this ∈ (10Mbps,10Gbps).
	+ Two insulated copper wires in a spiral, twisted to reduce electrical interfearence from other nearby pairs.
+ Coaxial cable
	+ Two copper conductors that are concentric (instead of being parallel like in twisted pair).
	+ Speed in the magnitude of 10 Mbps. 
+ Fiber optic cable
	+ Conducts pulses of light, each pulse representing a bit. Speed can be in the magnitude of 100Gbps.
	+ Preferred long-haul transmission media (like for overseas transmission) because they are immune to electromagnetic interference, have low signal attenuation, and are very hard to tap.

##### Unguided Media
+ Terristrial radio channels
	+ Carry signals in the electromagnetic spectrum.
	+ Attractive medium because they require no physical installation, can penetrate walls, can provide connectivity to mobile user, and carry signals for long distances.
	+ Environmental considerations play role in path lass, shadow fading, multipath fading, and interfearence.
	+ Classified in three groups on basis of range:
		+ Personal area (1m-2m): Personal devices like wireless headphones/keyboard use this.
		+ Local area (10m-500m): Wireless LAN (WiFi) operate in this range.
		+ Wide area (10s of km): Cellular access technologies (3G, LTE) operate in this range.
+ Satellite channels
	+ Communication satellite links two or more Earth-based microwave transmitter/receivers (known as ground stations).
	+ Two types of satellite are majorly used in communications:
		+ Geostationary satellites
			+ They remain permanently above the same spot on earth (in an orbit of 36,000km above earth).
			+ Signal propogation delay of 280ms. Operate at speed of 100s of Mbps.
		+ Low-earth orbitting satellites
			+ They are placed much more closer to earth, hence they rotate around from earth's pov.
			+ Hence, to provide continuous coverage to an area, need many LEO satellietes.

___

### 1.3 The Network Core

#### 1.3.1 Packet Switching
+ Most packet switches use "store-and-forward-transmission". 
+ The packet switch should first retrieve the entire packet from the incoming link before it can began transmitting the first bit of the packet to the outbound link.
+ Store-and-forward introduces transmission delays at every link of the packet route. 

##### Transmission delay | Packetization delay | Store-and-forward delay 
+ Packet size = L bits 
+ Transmission rate for all devices involved = R bits/second 
+ **Transmission delay for one packet over one link = L/R seconds**.
+ Number of links between the end-systems = N 
+ **Transmission delay for one packet over N links = NL/R seconds** 
+ For each new packet, the 'additional' delay added would be L/R seconds.
+ Therefore, additional transmision delay caused by P-1 packets = (P-1)L/R seconds.
+ **Transmission delay for P packets over N links = (N+P-1)L/R seconds**.

##### Queuing delay and Packet Loss
+ For each outgoing link of the packet switch, it maintains an output buffer/output queue.
+ If an arriving packet needs to be transmitted to a link that is busy with the transmission of another one, then the incoming packet will have to wait in the corresponding output buffer. 
+ This causes output buffer queuing delays.
+ This delay is variable and depends on the level of congestion in the network. 
+ Further, when an incoming packet arrives and the output buffer for the link that it is meant to go through is already full, then "packet loss" occurs. Either the new-arriving, or one of the already-queued packet, gets dropped.

##### Forwarding Tables and Routing Protocols 
+ In the internet, every end system has an IP address.
+ Like postal codes, IP addresses follow a hierarchical structure.
+ Each router has a forwarding table that maps destination addresses (or portions of the destination addresses) to that router’s outbound links. 
+ When a new packet arrives at a router, it examines the packet's destination address. Then the router searches its forwarding table for the packet's destination IP (or the relevant portion of the packet's destination IP), finds the appropriate outbound link, and directs the packet there. 
+ Routing Protocols are used to automatically set upthe forwarding tables for a router (Eg: RIP, OSPF, EIGRP, BGP :)

#     
<!--Empty Heading-->  

#### 1.3.2 Circuit Switching 
+ In circuit-switched systems, the resources needed along the path for endsystems to communicate are reserved for the duration of their communication. 
+ For example, in traditional telephone networks, the network establishes a "circuit" and reserves a constant transmission rate in the network’s links for the duration of the call. 
+ This is in contrast to packet switched systems, where resources were consumed "on demand". As a consequence, when congestion occured there, some packets would have to wait for their turn. 

##### Frequency Division Multiplexing 
+ The frequency spectrum of the link is divided into bands and the link dedicates a specific frequency band to each connection for the duration of the call.
+ The width of these bands (bandwidth) are usually 4kHz. 
+ FM radio stations use FDM. They are usually allocated a frequency band in the (88MHz-108MHz) spectrum.

##### Time Division Multiplexing
+ Time is divided into "frames" of fixed duration, and each frame is further divided into a fixed number of slots. 
+ When a new connection is opened on the link, the link dedicates a slot in every frame to this new connection.

##### Packet Switching vs Circuit Switching
+ Critics of CS/proponents of PS say that:
	+ CS is wasteful because dedicated circuits are underutilized/sit-idle during silent periods. In comparision, PS offers better sharing of transmission capacity and is more efficient (as it can accommodate more users and transmit "bursts" of data faster).
	+ In CS, establishing end-to-end circuits and reserving end-to-end capacity is complicated and requires complex software to coordinate switches along the path. In comparision, PS is simpler and less costly to implement.
+ Critics of PS/proponents of CS say that:
	+ PS is not suitable for real-time services (like calls) because of its variable and unpredictable end-to-end delays. In contrast, CS can provide service with more reliability.

#
<!--Empty Heading-->       

#### 1.3.3 A Network Of Networks
+ ISPs are categorized in a multi-hierarchy structure on the basis of how big they are. 
+ There is no authority that determines the status of the tiers, but commonly accepted definition is:
	+ **Tier 1 ISPs (Global ISPs)** - who can reach every other network on the Internet without purchasing IP transit or paying for peering. Their are close to a dozen ISPs at this level.
	+ **Tier 2 ISPs (Regional ISPs)** - Networks that peer for free with some networks, but still purchases IP transit or pays for peering to reach at least some portion of the Internet.
	+ **Tier 3 ISPs (Access ISPs)** - Network that solely purchases transit/peering from other networks to participate in the Internet.
+ Access ISPs pay the Regional/Global ISPs with whom they peer with (in order to use their network). Similarly, Regional ISPs pay the Global ISPs with whom they peer. Hence, all across the hierarchy, there is a provider-customer dynamic.

##### Terms Involved In The Internet Infrastructure 
+ **Points of Presence (PoPs)** - A group of one or more routers (at the same location) present in the service area of the provider ISP, where the customer ISPs can connect to it.
+ **Multi-home** - When a customer ISP connects to two or more provider ISPs (so that its services still continue in case of an outage in one of its providers). 
+ **Peering** - Sometimes, to reduce costs, ISPs at the same level of the hierarchy "peer" together, settlement free, so that the traffic between them passes directly through this link (instead of going through upstream intermediaries).
+ **Internet Exchange Points (IXP)** - A dedicated meeting point where multiples ISPs can peer together. It is usually a stand-alone building with its own switches. There are 600+ IXPs globally.
+ **Content Provider Networks** - Companies building a private network for connecting the servers in their private data centres (Eg: Google). 
	+ Their private TCP/IP network only carries data to/from their own servers. 
	+ Content provider's private networks attempts to "bypass" the upper tiers of the ISPs as much as it can, by peering settlement free and directly with lower tier ISPs. 
	+ However,  they have to connect with some Tier-1 ISPs and pay them for the traffic it excahnges with them.
	+ By creating their own network, a content provider vastly reduces its dependence on the top tier ISPs (along with reducing its payments to them as well).  

___

### 1.4 Delay, Loss, and Throughput in Packet Switched Networks

#### 1.4.1 Overview of Delay in Packet Switched Networks
**Total delay = Processing delay + Queuing delay + Transmission delay + Propagation delay**

##### Processing Delay
+ Time required to examine the packet's header and determine which outbound link to send it to is called processing delay.
+ It also includes time required to check for bit-level errors that may have crept into the packet.
+ In high-speed routers, processing delay is usually in order of microseconds or less.

##### Queuing Delay
+ A packet experiences queuing delay when the outbound link it is meant to go through is currently being used to transmit another packet.
+ The length of the delay for a packet depends on the number of packets waiting in the queue before it.
+ Number of packets that an arriving packet might expect to find is a function of the intensity and nature of the traffic arriving at the queue.
+ Queuing delays can be on the order of microseconds to milliseconds in practice.

##### Transmission Delay
+ A packet can only be transmissed once the router recieves all of its bits. Hence, there is transmission delay at each new link (or at every router).
+ Assuming size of packet to be L bits, and transmission rate of the link to be R bits/seconds, then transmission delay faced by the packet in the link will be L/R seconds.
+ Transmission delays are typically on the order of microseconds to milliseconds in practice.

##### Propagation Delay
+ Propogation delay is the time taken by a bit from when it is pushed into the link, till it reaches its destination.
+ The bit propogates as the propagation speed of the link. The propogation speed depends of physical medium of the link.
+ If the length between two routers is d metres, and the propagation speed of the link is s metres/second, then the propagation delay will be d/s seconds.
+ In wide-area networks, propagation delays are on the order of milliseconds. 

#
<!--Empty Heading-->  

#### 1.4.2 Queuing Delays and Packet Loss
+ Unlike the other three delays, the queueing delay can vary significantly from packet to packet.
+ Hence, statistical measures are used to characterise queuing delay (average delay, variance of delay, probability that delay exceeds a specified value).
+ Queuing delay depends on various factors like:
	+ Rate at which traffic arrives at the queue.
	+ The transmission rate of the link. (if is is less than the traffic rate for any period of time, then queues will start building).
	+ Nature of the incoming traffic (steady vs bursts).

##### Traffic Intensity
+ Assume rate at which traffic arrive in the queue = a packets/second
+ Size of each packet = L bits/packet
+ Transmission rate of the queue = R bits/second
+ **Traffic Intensity = La/R**
+ Traffic Intensity plays a vital role in estimating the extent of queueing delay:
	+ If La/R > 1, average rate of arrival is greater than average rate of transmission => queue will keep increasing and so will queuing delay. 
	+ Lesson: **Design your system so that the traffic intensity is no greater than one**.  
	+ If La/R <= 1, the queuing delay depends on the nature of the incoming traffic.
		+ If packets arrive steadily, they are more likely to find empty queues and might pass through the router with no queuing delay.
		+ If packets arrive in bursts, there will be a significant amount of average queuing delay.
	+ Traffic intensity alone isn't enough to characterise queuing delay (as nature of arriving traffic needs to be considered too), however it gives an intuitive understanding. 
		+ If La/R ~ 0, arriving packets are fewer and far in between and being transmitted fast enough for the queue to empty/relatively short. 
		+ If La/R ~ 1, there can be intervals of time when arrival rate > transmission rate, when queues will form and lenthen, while at other intervals of time when arrival rate < transmission rate, the queues will shrink.  
		+ When La/R -> 1, average queue gets larger and larger and queueing delay increases rapidly.

##### Packet Loss
+ Queues have a finite holding capacity. Due to the finite capacity, the queue can only grow uptil a point.
+ When a new packet arrives and the queue is already full, the router simply drops the packet, and the packet is lost. 
+ Therefore, the queueing delay doesn't increase after a point, instead, the fraction of lost packets does.
+ Hence, performance at a node is often measured not only in terms of delay, but also in terms of the probability of packet loss.

#
<!--Empty Heading-->  

#### 1.4.3 Endsystem Delays
+ There can be some other kinds of delays in the end system apart from the ones discussed. 
+ An end-system using a shared medium to connect to the internet (wifi or cable modem), might purposefully delay its transmission as part of its sharing protocol.
+ Media packetization delay: In Voice-over-IP applications, the sending side must first fill a packet with encoded digitized speech before passing the packet to the internet. This can cause significant delay and impact user-percieved quality of the service.

#
<!--Empty Heading-->

#### 1.4.4 Throughput in Computer Networks 
+ Apart from delay and packet loss, end-to-end throughput is another critical performance measure in computer networks.
+ Instantaneous throughput is defined as the rate (in bits/second) at which the destination is recieving the required packets.
+ Average throughput, for a file of size F bits that takes T seconds to reach the destination host, will be F/T bits/second.
+ Delay and throughput are more important in varying situations:
	+ For calls, it's desirable to have low delay and the instantaneous throughput consistently above a certain threshold.
	+ For file transfer, delay might not be critical but it will be desirable to have the highest possible average throughput.
+ For a simple network, the transmission rate of the bottleneck link will be the constraining factor for the throughput.
	+ The network core usually has links with very high transmission rates, hence the bootleneck link in an uncongested network is usually the access link.
	+ However, for a congested network, where the network core is facilitating multiple connections, then its average transmission rate for one connection can drop significantly. If it drops below the transmission rate of the access link, then it becomes the bottleneck. 

___

### 1.5 Protocol Layers and their Service Models

#### 1.5.1 Layered Architecture
+ A layered architecture allows us to discuss a well-defined, specific part of a large and complex system.
+ As per the layered architecture, each layer, combined with the layers below it, implements some functionality. 
+ Each layer provides its service to the layer above it by: 
	+ Performing certain actions within that layer, and 
	+ Using the services of the layer directly below it.
+ This layered-architecture also provides modularity. 
	+ The layering makes it easier to change the implementation of the service provided by a specific layer without those changes affecting the rest of the system. Because, 
		+ As long as the layer provides the same service to the layer above it as it used to before, and 
		+ Uses the same services from the layer below it as it used to before, then 
		+ The remainder of the system remains unchanged when a layer’s implementation is changed.
	+ For large and complex systems that are constantly being updated, the ability to change the implementation of a service without affecting other components of the system is extremely helpful.

##### Protocol Stack
+ When taken together, the protocols of the various layers are called the "protocol stack".
+ The internet architecture can be broadly divided into 5 layers (Five-layered Internet Protocol Stack):
	+ Application layer
	+ Transport layer
	+ Network layer
	+ Link layer
	+ Physical layer
+ However, earlier, ISO's OSI reference stack had 7 layers. Following were the two additional stacks that were just below the Application layer:
	+ Presentations (data compressions, encryption, description),
	+ Session (sync data exchanges, and provide checkpints for recovering scheme).
+ In the present model, it is on the application developer to decide if an application requires the services that the presentation and session layers provided. (In case they are, it's up to the develper to build those functionalities into the application).

##### Application Layer | Application layer packet is called a message.
+ This is where network applications and their application-layer protocols reside. 
+ Some commonly used ones are:
	+ HTTP (Hyper Text Transfer Protocol) - For web requests and responses
	+ SMTP (Simple Mail Transfer Protocol) - Transfer of email messages
	+ FTP (File Transfer Protocol) - Transfer of files between two end-systems
	+ DNS (Domain Name Service) - Translate web-urls to IP addresses.
+ An application-layer protocol is distributed over multiple end systems, with the application in one end system using the protocol to exchange packets of information with the application in another endsystem.

##### Transport Layer | Transport layer packet is called a segment.
+ This layer is responsible for transporting application-layer messages between application endpoints.
+ There are two main transport layer protocols:
	+ TCP (Transmission Control Protocol)
	+ UDP (User Datagram Protocol)
+ TCP provides a connection-oriented service to its applications, including: 
	+ Reliability - it provides gurenteed delivery of messages to the destination.
	+ Flow-control between sender and reciever.
	+ Congestion control mechanism in the network.
+ UDP provides a connectionless service to its applications. It is a no-frills service that provides 
	+ No reliability - it provides best-effort delivery of messages to the destination. 
	+ No flow control between sender and reciever.
	+ No congestion control in the network.

##### Network Layer | Network layer packet is called a datagram.
+ The transport-layer protocol (TCP/UDP) in a source host passes a transport-layer segment and a destination address to the network layer, which delivers the segment to the transport layer in the destination host.
+ The network layer contains the IP Protocol, which defines the fields in the datagram and how the end systems/routers act on these fields.
+ There is only one IP protocol, and all internet components that have a network layer must run the IP protocol.
+ Along with the IP protocol, the network layer also contains various routing protocols (which determine the routes that datagrams take between sources and destinations).

##### Link Layer | Link Layer packet is called a frame.
+ The network layer routes a datagram through a series of routers. In order to move a packet from one node to the next, the network layer relies on the services of the link layer.
+ At each node, the network layer passes the datagram to the link layer, which delivers the packet to the network layer of the next node.
+ Services of the link layer vary as per the specific link-layer protocol that is being employed. 
	+ Eg: Some link layer protocols provide reliable delivery from one node to another (which is different from what TCP provides, as its reliable delivery is from endsystem to endsystem.)  
+ Some link layer protocols are:
	+ Ethernet
	+ Wi-fi
	+ Cable access network’s DOCSIS protocol

##### Physical Layer
+ While the job of the link layer is to move entire frames from one network element to an adjacent network element, the job of the physical layer is to move the individual bits within the frame from one node to the next. 
+ The protocols in this layer are dependent on the transmission medium of the link.

#
<!--Empty Heading-->

#### 1.5.2 Encapsulation
+ At the sending host, 
	+ The application-layer message (M) is passed to the transport layer, which adds a transport-layer header (Ht), to make it a segment (Ht M).
	+ The transport-layer segment (Ht M) is passed to the network layer, which adds a network-layer header (Hn), to make it a datagram (Hn Ht M).
	+ The network-layer datagram (Hn Ht M) is passed to the data link layer, which adds a link-layer header (Hl), to make it a frame (Hl Hn Ht M).
	+ The link-layer frame (Hl Hn Ht M) is transported node to node, bit by bit, with the help of the physical layer.
+ Hence, we can see that at each layer, a packet has two types of fields:
	+ Header fields - which contain the data required for the layer to provide its service.
	+ Payload field - which typically encapsulates the packet from the layer before.
+ Encapsulation is usually more complex than this, as 
	+ A large message may be divided into multiple transport-layer segments.
	+ Each of which may be divided into multiple network-level datagrams.
	+ At the recieving end, the consituent datagrams must then be used to reconstruct the segments.
	+ And those segments would be used to reconstruct the message.

##### Packet swiches 
+ Routers and Switches are both packet switches.
+ Switches are layer 2 devices (data link layer), while routers are layer 3 (network layer).
+ Hence, routers can recognize layer 3 addresses (IP address), while switches can't. 
+ However, switches can still recognize layer 2 addresses (like the Ethernet address, MAC address). 

___

### 1.6 Networks Under Attack

#### 1.6.1 Malware
+ Malware is any malicious software that is designed to enter and infect our devices.
+ Malware can do many things once it is inside a system, including:
	+ Delete files.
	+ Install spyware that collects private information and sends it back over the internet.
	+ Enroll our compromised host in a network of similarly compromised devices (called botnet) and be used for spam e-mail or ddos attacks.
+ Most of the malware is self-replicating (that is, after infecting a host it looks for ways to infect other hosts connected to it).
+ Malware can spread in the form of viruses or worms.
	+ **Viruses**
		+ They need some form of user interaction to infect the user's device.
		+ Eg: Email attachmens containing malicious attachments.
	+ **Worms**
		+ A kind of malware that can enter the device without any explicit user interaction.
		+ Eg: Through a vulnerable network application.

#
<!--Empty Heading-->

#### 1.6.2 Denial of Service (DoS)
+ A Denial-of-Service attack renders the network, host, or other piece of infrastructure unusable by legitimate users.
+ Most DoS attacks fall under one of the following:
	+ **Vulnerability attack** - Sending well-crafted and targetted messages to a vulnerable application or OS, in order to stop the service or crash he host.
	+ **Bandwidth flooding** - Sending a deluge of packets to the targeted host, so that the target’s access link becomes clogged, and legitimate packets are not able to reach the host.
	+ **Connection flooding** - Establishing a large number of half-open or fully-open TCP connections at the target host, which becomes so bogged down by by the bogus connections that it stops accepting legitimate ones.
+ When doing bandwidth flooding, the attacker just needs to send data to the router at the rate equal to or higher than its access rate. 
	+ A single attack source may not be able to generate enough traffic, and
	+ If the source of all the data is just one system, then an upstream router might just block it because of suspicion.
	+ Hence, attackers usually deploy a "distributed denial of service" (DDoS) attack.

#
<!--Empty Heading-->

#### 1.6.3 Packet Sniffing
+ Ubiquitous internet access is extremely convinient, but also vulnerable from a security point of view.
+ Someone can place a passive receiver, called a "**packet sniffer**", in the vicinity of a wireless transmitter. The packet sniffer will then recieve a copy of every packet that passes through the transmitter.
+ Sniffers can be placed in wired environments too (that pick up on LAN broadcasts or sniff packets passing from a router).
+ After the packets are sniffed, they can be analysed offline for sensitive information.
+ As packet sniffers are passive, they are hard to detect. 
+ Some of the best defenses against packet sniffing involve cryptography (as they are able to shield the contents of the packets even if the packets themselves get sniffed).

#
<!--Empty Heading-->

#### 1.6.4 IP Spoofing
+ IP spoofing is when someone inject packets into the Internet with a false source address. 
+ It is possible to create a packet with an arbitrary source address, packet content, and destination address. When this packet is sent to the internet, it gets forwarded and reaches the destiation, where an unsuspecting reciever might believe the false packet to have come from the legitimate source.
+ IP spoofing is one of many ways in which one user can masquerade as another user. 
+ To solve this problem, we use end-point authentication mechanisms, which provide a way to authenticate the source from which the packet is coming. 

#
<!--Empty Heading-->

#### 1.6.5 Why is Internet so Insecure?
+ The internet was originally built on the assumption of trust, and hence designed on the model of “a group of mutually trusting users attached to a transparent network”. 
+ Many aspects of the original Internet architecture deeply reflect this notion of mutual trust.
	+ Ability of a user to send a packet to any other user is the default, instead of a request/grant mechanism.
	+ Update messages for routing tables are often implemented without verifying if they are true or not.
+ The model of mutual trust led to an architecture which is extremely vulnerable to security attacks.
+ Today's internet does not consist of "mutually trusting users", as the increasing number of cyber-security attacks have pushed them to distruct the hardware, the software, and even the air through which they communicate.
+ Today, communication among mutually trusted users is the exception rather than the norm.
+ Welcome to the world of modern computer networking. 

___

### 1.7 History of Computer Networking and the Internet

#### 1.7.1 The Development of Packet Switching: 1961-72
+ In the 1960s, the telephone network based on circuit switching was the world's dominant computer network. 
+ Circuit switching was an appopriate mechanism as it voice on calls were transmitted at a constant rate.
+ However, with the advent of computers and the need of connecting them in networks, it was felt that there should be a better design for handling "bursty" traffic more efficiently (interval of activity followed by periods of inactivity). 
+ Three research groups, each unaware of each others' works, began inventing packet switching as an efficient alternative. Their work laid the foundations for today's internet: 
	+ Leonard Kleinrock (MIT), 
	+ Paul Baran (Rand Institute), and 
	+ Donald Davies and Roger Scantlebury (NPL). 
+ J. Licklider and Lawrence Roberts, from MIT, went on to lead the computer science program at the Advanced Research Projects Agency (ARPA), which eventually led to the **ARPAnet** - the first packet switched computer network and and a direct ancestor to today's public Internet.
+ The first host-to-host protocol between ARPAnet end systems was known as the **Network Control Protocol (NCP)** [RFC 001].

#
<!--Empty Heading-->

#### 1.7.2 Proprietary Networks and Internetworking: 1972–1980
+ The initial ARPAnet was a single closed network. 
+ Soon, additional stand-alone packet-switching networks besides ARPAnet came into being:
	+ ALOHANet - a microwave network linking universities on the Hawaiian islands.
	+ DARPA’s packet-satellite and packet-radio networks. 
	+ Telenet - a BBN commercial packet switching network based on ARPAnet technology). 
	+ Cyclades - a French packet-switching network 
	+ Time-sharing networks such as Tymnet and the GE Information Services network
	+ IBM’s SNA, which paralleled the ARPAnet work.

##### Internetworking
+ With all the standalone networks, there felt a need to develop an encompassing architecture connecting the networks together.
+ Vinton Cerf and Robert Kahn did pioneering work on interconnecting networks (under the spnsorship of DARPA).
+ Their work led to the concept of *network of networks*, which they described with the term **"internetting"**.

##### TCP/UDP/IP
+ Those architectural principles were embodied in early versions of TCP. 
+ The early version of TCP combined a reliable in-sequence delivery of data via end-system retransmission (still part of today’s TCP), with forwarding functions (which today are performed by IP).
+ A need was felt for an unreliable, non-flow-controlled, end-to-end transport service for applications such as packetized voice, which led to separation of IP out of the then-TCP protocol, and development of the UDP protocol.
+ The three key Internet protocols that we see today — TCP, UDP, and IP — were conceptually in place by the end of the 1970s.

##### Ethernet Protocol
+ Alongside, other key networking activities were going on. 
+ Norman Abramson developed ALOHAnet, and the ALOHA protocol was the first multiple-access protocol. 
+ It allowed geographically distributed users to share a single broadcast communication medium (a radio frequency).
+ Metcalfe and Boggs built on this multiple-access protocol work when they developed the Ethernet protocol for wire-based shared broadcast networks.
+ The Ethernet Protocol was the foundation for today’s PC LANs.

#
<!--Empty Heading-->

#### 1.7.3 A Proliferation of Networks: 1980–1990
+ By end of 1970s, 200 hosts were connected to the ARPAnet. By the end of 1980s, the number of hosts connected to the public Internet would reach a hundred thousand. 
+ The tremendous growth happened because of several distinct efforts that aimed at creating computer networks linking universities together. 
	+ BITNET provided e-mail and file transfers to several universities.
	+ CSNET was formed to link university researchers who did not have access to ARPAnet.
	+ NSFNET was created to provide access to NSF-sponsored supercomputing centers.
	+ By the end of the decade, NSFNET's served as a vital component that linked regional networks.
+ In the ARPAnet community, many of the final pieces of today’s Internet architecture were falling into place.
	+ In 1983, TCP/IP was officially deployed and became the new standard host protocol for ARPAnet (replacing the NCP protocol).
	+ In late 1980s, important extensions were made to TCP to implement host-based congestion control.
	+ DNS was developed to map between a human-readable Internet names to their 32-bit IP addresses.

##### Minitel 
+ Along the same time, the French launched the "Minitel project".
+ It had the ambitious aim to bring data networking to everyone's homes.
+ It consisted of a public packet-switched network, Minitel servers, and inexpensive terminals that had built-in low-speed modems.
+ The French government gave away a free Minitel terminal to each French household that wanted one.
+ Minitel sites included free sites—such as a telephone directory site—as well as private sites, which collected a usage-based fee from each user.
+ At its peak in the mid 1990s, it offered more than 20,000 services, ranging from home banking to specialized research databases. 
+ The Minitel was in a large proportion of French homes 10 years before most Americans had ever heard of the Internet.  

#
<!--Empty Heading-->

#### 1.7.4 The Internet Explosion: The 1990s
+ The 1990s saw the commercialization of the Internet.
	+ ARPAnet ceased to exist. 
	+ In 1991, NSFNET lifted its restrictions on the use of NSFNET for commercial purposes. 
	+ NSFNET itself was decommissioned in 1995, with Internet backbone traffic being carried by commercial Internet Service Providers (ISPs).

##### World Wide Web
+ The development of the World Wide Web was a key event, as it brought the Internet into the homes and businesses of millions of people worldwide.
	+ The Web was invented at CERN by Tim Berners-Lee between 1989 and 1991.
	+ Berners-Lee and their associates developed initial versions of HTML, HTTP, a Web server, and a browser — the four key components of the Web.
+ Several researchers were developing Web browsers with GUI interfaces, including Marc Andreessen, who along with Jim Clark, formed Mosaic Communications, which later became Netscape Communications Corporation (and still lives in spirit as Mozilla Firefox <3).

##### Rise of Internet Companies
+ The second half of the 1990s was a period of tremendous growth and innovation for the Internet, with major corporations and thousands of startups creating Internet products and services, of which four of the biggest were:
	+ E-mail, including attachments and Web-accessible e-mail.
	+ The Web, including Web browsing and Internet commerce.
	+ Instant messaging, with contact lists.
	+ Peer-to-peer file sharing of MP3s, pioneered by Napster.
+ Interestingly, the first two applications came from the research community, whereas the other two were created by entrepreneurs.
+ A number of Internet giants were founded in this period, including Microsoft, Cisco, Yahoo, e-Bay, Google, and Amazon.

#
<!--Empty Heading-->

#### 1.7.5 The New Millennium
+ Innovation in computer networking grows at great pace. Some of the fronts are mentioned in the following sub-sections.

##### In the Network Edge
+ Deployments of faster routers and higher transmission speeds in both access networks and network backbones.
	+ Aggressive deployment of broadband internet access to homes (not just DSL but also FTTH). 
	+ Ubiquitous access of high-speed public Wi-Fi networks. 
	+ Easy access to medium-speed 4G cellular networks. 
+ This high speed access sets the stage for various applications like:
	+ User generated video (YouTube)
	+ On-demand streaming (Netflix)
	+ Video Conferencing (Skype, Zoom, GMeet)
	+ Social Networks (FB, Insta, Twitter)

##### In the Network Core 
+ Deploying extensive private data centres (Google and Microsoft), which not only help the companies peer directly with lower-tier ISPs but also helps them provide services at a faster speed (making their search, mail, etc faster).
+ Deploying applictions on cloud and offering that as a service: 
	+ Amazon AWS
	+ Microsoft Azure
	+ Google Cloud Platform

___









