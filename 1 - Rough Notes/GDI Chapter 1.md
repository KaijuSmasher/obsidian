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
	- Transmission of unstructured bit-streams through physical connections
	- Transmission is unreliable
- Core Points:
	- Description of:
		- Parameters like distance, signal voltage, bit times, bit encoding
		- Design of mechanical parts like cables, transceivers, pins
	- Systems don't translate bits: Sending and receiving bits by antenna, network cards, modems, ISDN-cards
	- Forwarding of bits:
		- Hub: copies bits from a link onto more other links
		- Repeater: freshens signals up by reading, rewriting and re-sending them, increases physical distance

### Simple Example
- A very simple layer operating at one megabit per second (Mb/s):
	- One bit is transmitted by sender every microsecond
	- One bit is received by receiver every microsecond
- Sender operation:
	- To transmit bit=1, set V=5 during one microsecond
	- To transmit bit=0, set V=-5 during one microsecond
- Receiver operation:
	- if V=5, bit=1 decoded
	- if V=-5, bit=0 decoded
- Possible problems:
	- Electromagnetic perturbations
	- Clock drift (one instance being faster than the other)

### Data Link Layer
- Task:
	- Medium Access Control (MAC): Controls who gets access to the write onto the physical layer
	- Logical Link Control (LLC): Flow control and reliable data transport inside of a network
- Core Points:
	- Creation of Frames: Structured groups of bits = Data packages
	- Checksum for failure recognition and correction
	- Synchronization
	- Access Control on shared media (Air in WLAN)
	- Protocols: CSMA/CD, CSMA/CA, Ethernet, Token-based, HDLC (High-Level Data Link Control), LLC (Logical Link Control IEEE 802.2), PPP (Point-to-Point Protocol),  etc
	- Devices:
		- Switch
		- Bridge
		- They interpret Data Link Layer Headers and relay frames or copy them selectively from one network to another
		- Increase distance of networks over physical barriers

### Bridge vs Switch
- Bridge: Enables different LANs with (possibly) different layer 2 technologies to exchange frames -> Example: Bus + Token Ring
- Switch: Connects nodes of same LAN technology by extra wires -> Example: Star

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
- Connection-less Service:
	- Unreliable transmission: frames can be lost
	- Transmission errors are usually detected
- Connection-oriented Service:
	- Reliable or unreliable transmissions

### What is a MAC Address?
The MAC-address is 48 Bits (6 Bytes) long in case of Ethernet or WLAN networks. The address is written in a hexadecimal format. It usually uses a byte by byte notation, separated by using "-" or ":" -> Example: 08-00-20-ae-fd-7e or 08:00:20:ae:fd:7e. The order of characters can also be different, there's the canonical and the "Bit-reversed"-representation. The canonical one is preferred.

A MAC-address is a unique 12-digit long hexadecimal number assigned to a network interface card (NIC) by the manufacturer. It acts as a unique physical or hardware address for devices on a local network (LAN) and is used to ensure data is routed correctly to the intended device.

### Network Layer
- Task:
	- Path-finding between end nodes on basis of source- and target-address
	- Sometimes construction, maintenance and dismantling of connections over multiple nodes
	- Communication over multiple networks with heterogenic technologies
- Core Points:
	- Data-packages: Packets
	- Fragmentation and de-fragmentation in case of packet being to long for Maximum Transfer Units (MTUs)
	- Devices:
		- Routers: interpret Network Layer Header and copy packets from one network to another
	- Protocols: 
		- IP, 
		- IPX

### IP Routers Connecting Different Technologies
![[Pasted image 20251020132811.png]]

### Transport Layer
- Task:
	- Provisioning of virtual end-to-end transmission between corresponding processes in end-systems
- Core Points:
	- Division of data-streams into segments (data-packets)
	- Connection-oriented transmission -> Example: TCP
	- Connection-less transmission -> Example: UDP
	- End-to-end flow-control
	- Congestion-control
	- Safe transmission: error-free information, not packet-loss, no packet duplication, order preservation
	- Mechanisms: Checksum, Sequence Numbers, Acknowledgements, Re-transmission
	- Protocols: UDP, TCP, SCTP, DCCP

### Session Layer
- Task:
	- Creates sessions between applications, manages them and closes them
	- Recovery of broken down connections
	- Searches for Services -> with the help of indexes
- Core Points:
	- Dialog-control: Sets and surveil's the rules for dialogs and data-transmission
	- Minimal functionality: connection creation, closing connection
	- Process synchronization: set back to synchronization points in case of error or recovery when connection breaks down
	- Examples: data backup and load distribution
	- Not available in most protocol suites

### Presentation Layer
- Task:
	- Data encryption
	- Data compression
	- Data conversion
- Core Points:
	- Application specific format transformation
	- Example: character set transformation EBCDIC <-> ASCII
	- Not available in most protocol suites

### Application Layer
- Task:
	- Everything which is not handled by the other layers
	- Manages syntax and semantics of messages to support the communication of application processes
- Core Points:
	- Application level protocols: SMTP, FTP, TELNET, HTTP, RTP
	- Enables the communication between application of different manufactorers -> Browsers, VoIP, etc
	- There are application layer gateways (ALGs), which encrypt and convert application protocols, transcoding of media-streams 

### TCP/IP Reference Model
![[Pasted image 20251020143718.png]]
- Alternative layering from the pov of the internet
- Applications are allowed to lay directly on the IP -> ICMP, IGMP, RSVP
- Session and Presentation layer are not available
- Physical and Data Link Layer fuse into the Network Access Layer
- Strong limitations: Transport = TCP/UDP, Mediation = IP

### Alternative Internet Protocol Stack
![[Pasted image 20251020144138.png]]
- Application: supporting network applications -> FTP, SMTP, HTTP
- Transport: host-host data transfer -> TCP, UDP
- Network: forwarding of packets from source to destination -> IP, routing protocols
- Link: data transfer between neighboring network elements
	- PPP, Ethernet
	- Comprises logical link control (LLC) and medium access control (MAC)
- Physical: bits "on the wire"

### Encapsulation
![[Pasted image 20251020144544.png]]

### Visibility of Layers alongside a path
![[Pasted image 20251020145513.png]]
- The Internet protocol (IP) enables the communication over the confines of heterogenic networks
- Baseline for data exchange on the internet

### Addresses within the Internet Protocol Stack
![[Pasted image 20251020145957.png]]
- Addresses (SAPs):
	- Port numbers
	- Protocol number
	- IP addresses
	- Layer-2 addresses (MAC addresses)
- Deployment of new applications:
	- Distribute software
	- usually use specific port for application and either UDP or TCP
	- Advertise IP address or DNS name

### The Hourglass Model
![[Pasted image 20251020150221.png]]

## Criticism of Reference Model
- ISO/OSI:
	- Uneven distribution of functions of the individual layers -> Presentation, Session, Application
	- Failed the implementation in real world
	- ITU-T is slow on standardizing new protocols
- TCP/IP:
	- Fast distribution over BDS/UNIX: good implementation, easy to use, for free
	- IETF fast on standardizing new protocols
	- Specific description of the status quo,  not general
- 5 Layer Model:
	- ISO/OSI without session and presentation layer
	- Most usable for taxonomies
- Danger: lowers the ways of thinking
- Allow no information exchange between layers
	- Cross Layer Design (CLD): Exchange of informations over possibly multiple layers
	- Examples: using physical layer information to optimize application layer, location-aware services, TCP reacts to ECN-bit (explicit congestion notification) in IP Header
- Classification of Protocols to specific layers sometimes problematic:
	- TCP/IP/MPLD/Ethernet: MPLS counts as layer 2.5
	- TCP/IP1/UMTS-Layers/IP2/Ethernet: IP is used in network and link layer -> only theoretic
- Example:![[Pasted image 20251020151729.png]]
- 