# Networking Principles

## Networks

### What is a network?
- A Network is a set of hardware and software that allows to transmit information from one sender to one or more receivers
- Current types of Networks:
	- Telephone
	- Broadcast
	- Mobile
	- Computer

Important to note is, that networks nowadays aren't really independent of each other anymore, mobile and computer networks have continued to develop and largely implemented the function of broadcast and telephone networks

### What is part of the internet?
- Millions of connected computer devices, also called hosts = end systems
- Communication Links:
	- Fiber
	- Copper
	- Radio
	- Satellite
	- Transmission rate = bandwidth
- Routers: used to forward data packages
- Protocols controlling the sending and receiving of MSGs like: TCP, IP, HTTP, FTP, PPP
- Running network applications
- Internet standards

In conclusion the internet, the Internet is a network of networks which is loosely hierarchical and split up into the public internet versus the private intranet. It's dependent on contracts which networks are connected with each other.

### Be aware of the difference
- The internet: is the physical infrastructure needed to transfer data world wide
- WWW: is the whole of the interconnected websites which can be accessed by using a browser

## Standardization

### What is it needed for?
It's needed to ensure the interoperability between all kinds of end systems 

### Examples for standardization bodies
- ISO: International Organization for Standardization
- DIN: Deutsches Institut für Normung
- ETSI: European Telecommunication Standards Institute
- IETF: Internet Engineering Task Force

### How do they operate?
These bodies usually operate by dividing areas into subdivisions and working groups, which in turn propose drafts that possibly end up becoming standards

## Network Classifications

### By geographical coverage
- Very small: nano communication networks
- 0.1 - 1m: internal bus/network, also Personal Area Network (PAN)
- 10m - 1km: Local Area Network (LAN)
- 1km - 100km: Metropolitan Area Network (MAN)
- 100km+: Wide Area Network (WAN)
- And even more: satellite networks, interplanetary networks, ...

### By topologies
- (Full) mesh:
	- Resilient against failures
	- Not economic for large number of nodes
	- Example: wifi adhoc network
	- ![[Pasted image 20251019173955.png]]
	- Important to note: Nodes do not have to be connected physically, there are also logically connected nodes, like in a wifi network, eliminating the cost
- Star:
	- Central switching node
	- Economic, not resilient
	- Example: Gigabit Ethernet
	- ![[Pasted image 20251019174249.png]]
	- Important to note: There can be multiple switching nodes, like having more switches connected to each other in a network
- Tree:
	- Hierarchy with a root
	- Not resilient
	- Example: telephone network
	- ![[Pasted image 20251019174358.png]]
	- Important to note: Can have redundancy so the broken off part doesn't completely suffer in case of failure
- Bus:
	- Used as common broadcast medium
	- All stations can send and receive packets
	- No forwarding by intermediate nodes needed
	- Requires multiple access protocols, e.g., CASMA/CD
	- Example: Standard Ethernet (1980/90)
	- ![[Pasted image 20251019174607.png]]
	- Important to node: It's very important to ensure that only one station is sending at one point in time so the signal being transported by the bus isn't overlapped by another
- Ring:
	- Nodes send, receive, and forward packets
	- Edges between neighbors: simplex or duplex
	- Can be resilient in case of duplex 
	- Requires multiple access protocols, e.g., time-division multiple access (TDMA) or token passing
	- Example: Token Ring
	- ![[Pasted image 20251019174926.png]]
	- Important to note: It's important to ensure that only the station carrying the toking is able to send, you also have to make sure that one station doesn't carry the token for too long

### Transmission Modes
- Unicast:
	- Message sent to *one* specific node
	- Aka point-to-point
	- Example: telephone
- Broadcast:
	- Message sent to *all* nodes within a network
	- Example: radio
- Multicast:
	- Message sent to *all* nodes of a defined group
	- Aka point-to-multipoint
	- Example: audio or video conferences
- Anycast:
	- Message sent to *one* node of a group of possible receivers
	- Example request to replicated content server

### Direction of usage
- Simplex:
	- Only into one direction
	- Example: pager
- Duplex:
	- Into both directions
	- At the same time
	- Example: telephone call
- Half-duplex:
	- Into both directions
	- Only one at a time
	- Example: Walkie-talkie

## Protocol Layers

### Example
![[Pasted image 20251019175737.png]]

### Instances and Protocols
- Service Data Unit (SDU):
	- Data to be carried from upper layer
- Protocol Data Unit (PDU):
	- Header info + SDU + trailer info
	- Header and trailer info contain, e.g. source, destination, checksums, etc.

### What is an open system:
An open system is an environment that ensures interoperability, portability and extensibility through open interfaces and specifications.

### What is an instance?
Expression of a layer inside an open system.
![[Pasted image 20251019180245.png]]

### What is a Protocol?
A protocol is an amount of rules, which define the format and the meaning of the packages and messages which are exchanged between instances on the corresponding layer. They are used to communicate between open systems and instances of the same layer have to implement the same protocols.

## Services

### Service and Service Access Point (SAP)
- Service: Set of primitives (operations) offered by a layer to a higher one
- Service Access Point (SAP): Service Access Point of a layer, the name or address of an instance used by a superordinate layer
- Primitives exchanged between SAPs
- Two N-SAPs communicate over layer N using an N-protocol and possibly establish an N-connection
- Example: TCP

### Example: Connection-Oriented Service
- Connection:
	- Creates a logical binding (connection) between to users
	- Users of a connection know of each other and share a common context
	- Useful for enhanced services: flow control, simplified forwarding, etc
- 3 phases of connection:
	- Connection setup
	- Data exchange
	- Connection teardown

## ISO/OSI Reference Model

### What is the ISO/OSI Model?
The ISO/OSI model is a very important theoretical model for communication layers. It was created and standardized between 1979 and 1983 by ISO. It's protocols usually begin with "X." , but they aren't relevant nowadays.

### OSI Layers
![[Pasted image 20251019183227.png]]

### Encapsulation Process
![[Pasted image 20251019183306.png]]

### Physical Layer
- Task:
	- Transmission of unstructured bitstreams through physical connections
	- Transmission is unreliable
- Core Points:
	- Description of:
		- Parameters like distance, signal voltage, bit times, bit encoding
		- Design of mechanical parts like cables, transceivers, pins
	- Systems don't translate bits: Sending and receiving bits by antenna, network cards, modems, ISDN-cards
	- Forwarding of bits:
		- Hub: copies bits from a link onto more other links
		- Repeater: freshens signals up, increases physical distance

### Data Link Layer
- Task:
	- Medium Access Control (MAC): Controls who gets access to the write onto the physical layer
	- Logical Link Control (LLC): Flow control and reliable data transport inside of a network
- Core Points:
	- Creation of Frames: Structured groups of bits = Data packages
	- Checksum for failure recognition and correction
	- Synchronization
	- Access Control on shared media
	- Protocols: CSMA/CD, CSMA/CA, Ethernet, Token-based, HDLC, LLC, etc
	- Devices:
		- Switch
		- Bridge
		- They interpret Data Link Layer Headers and relay frames or copy them selectively from one network to another
		- Increase distance of networks over physical barriers

### Bridge vs Switch
- Bridge: Enables LANs with (possibly) different layer 2 technologies to exchange frames
- Switch: Connects nodes of same LAN technology by extra wires -> Star topology

### Two Types of Data Link Layers
- WAN type data link layers (PPP, HDLC):
	- Reliable exchange of frames between two hosts attached to the same "link"
	- Mainly used by wide area networks
- LAN type data link layers (Ethernet, Token Ring, FDDI, WiFi, Wimax):
	- Exchange of frames between hosts attached to the same LAN
	- Limited geographical coverage

### Service of Data Link Layer
![[Pasted image 20251019193124.png]]
- Transmissions of frames between hosts directly connected at the physical layer or directly attached to the same LAN
- Most data link layers have a maximum frame length
- Connectionless Service:
	- Unreliable transmission: frames can be lost
	- Transmission errors are usually detected
- Connection-oriented Service:
	- Reliable or unreliable transmissions

### What is a MAC Address?
