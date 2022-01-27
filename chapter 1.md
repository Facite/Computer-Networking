# Chapter 1: Computer Networks and the Internet

### 1.1 What is Internet?

##### The Internet
+ Can be thought of as a computer network that interconnects billions of computing devices around the globe.
+ It can also be thought of as an infrastructure that provides services to applications.
	+ End systems attached to the Internet provide a "socket interface". 
	+ This interface specifies how a program running on one end system can ask the 'Internet infrastructure' to deliver data to a specific destination program running on another end system.

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
+ To connect devices acress the globe, need common standards.
+ Internet standards are developed by the Internet Engineering Task Force (IETF)
+ Their standard documents that detail protocols are called Requests for Comments (RFCs)
+ The IEEE 802 LAN/MAN Standards Committee specifies the Ethernet and wireless WiFi standards.

##### Network Protocols 
+ All activities on the internet involving two or more interconnected remote entities are governed by a protocol.
+ A protocol defines the format and the order of messages exchanged between communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.
+ Mastering the field of computer networking is equivalent to understanding the what, why, and how of networking protocols.

____

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

#### 1.3.2 Circuit Switching 

