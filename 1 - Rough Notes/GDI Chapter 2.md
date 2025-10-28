# Network Layer

## The Network Layer

### What is the Network Layer?
![[Pasted image 20251028130329.png]]
- Goal: forwards packets from any source to any destination through heterogeneous networks and routers
- End host = equipment able to:
	- Send and receive packets originated by or destined to it
- Router = equipment able to:
	- Send and receive packets originated by or destined to it
	- Forward other packets towards their destination, in particular across network borders and over networks of different technology
- A router must have several interfaces
- An end host (e.g. a server) may have several interfaces, but never relays packets
### Basic Principles
- Network layer service independent of link layer service
- Each interface of a host/router identified by a network layer address
- Network layer conceptually divided in two planes:
	- Data plane contains the protocols and mechanisms that allow hosts and routers to exchange packets carrying user data
	- Control plane contains the protocols and mechanisms that enable routers to efficiently learn how to forward packets towards their final destination (e.g. routing protocols, protocols for connection setup and teardown)
- Two possible organizations:
	- Connectionless service (datagram transmission mode) -> Example: IP technology
	- Connection-oriented service (virtual circuit mode) -> Example: MPLS technology

### Datagram Transmission Mode
- Packets:
	- Called datagrams
	- Contain source address, destination address, payload
- Destination-based forwarding:
	- Forwarding table contains:
		- Destination address or prefix
		- Corresponding outgoing interface
	- Upon packet arrival:
		- Router consults forwarding table
		- To decide through which interface a packet should be sent depending on its destination address
- Examples:
	- IP (IPv4 and IPv6)
	- CLNP (Connectionless Network Protocol)
	- IPX (Internetwork Packet eXchange from Novell)
- The forwarding tables of all routers must be coherent to ensure that a packet sent by any source will reach its destination
![[Pasted image 20251028131520.png]]
Question: How are forwarding tables build?

### Routing and (Destination-Based) Forwarding
- Forwarding:
	- Uses forwarding table to move packets from router's input to appropriate output interface
	- Forwarding tables determine route taken by packets from source to destination
- Routing:
	- Provides all routers with the information that allows them to build their routing tables
	- Possibly several routing tables are combined to a single forwarding table
	- Usually distributed algorithm
- Analogy
	- Routing: setting up direction signs at road intersections
	- Forwarding deciding directions at intersections while driving
- ![[Pasted image 20251028132032.png]]

### Routing Principles
- Static routing:
	- Network manager or network management station computes all routing tables and downloads them on all routers
	- How to compute routing tables?
		- Shortest path algorithms
		- More complex algorithms for load balancing or traffic engineering
	- Advantages: Easy to use in a small network
	- Drawbacks: Does not deal with link and router failures
	- Adopted by "software-defined networking"
- Dynamic routing:
	- Routers exchange messages and use a distributed algorithm to build their routing tables:
		- Links possibly associated with administrative link costs
		- Traffic follows least-cost or shortest paths
	- Used in most networks
	- Most common methods
		- Distance vector routing
		- Link state routing
	- Advantages: Can easily adapt routing tables to changes, e.g., failures
	- Drawbacks: More complex to implement than static routing

### Examples for Datagram Transmission Mode 
- Ethernet
	- MAC addresses (6 bytes)
	- Forwarding tables populated by learning bridges
		- Record where pkts with certain src MAC come from
		- Use this info for forwarding pkts with certain dest addresses
	- When no entry matches a dest address, pkt is flooded
- IP Technology
	- IP addresses (4 or 16 bytes)
	- Forwarding tables populated by configuration or routing algorithms
		- IP address prefixes used instead of individual addresses as destinations
		- Contain "next hops"
		- Default entry exists

### Virtual Circuit Mode 
![[Pasted image 20251028133616.png]]
- Virtual circuit (VC)
	- Connection established from source to destination through all routers along the path
	- Has VC identifier (VCI)
		- Used in forwarding rules for VC installed in all forwarding tables on the way
		- Packets are equipped with VCI which is used for forwarding decisions
- Forwarding table
	- Contains information per VC
	- Forwarding decisions taken only at VC setup
		- Objective: simplified forwarding
	- Used to forward all packets of VC
		- All packets follow same path (good for traffic engineering)
- Examples: ATM, X.25, Frame Relay, MPLS, GMPLS

### Routing Options for CV Setup
 ![[Pasted image 20251028134143.png]]
- Hop-by-hop routing
	- Each router consults its forwarding table to forward VC setup message
- Source routing / explicit routing
	- Source (or first hop router) indicates the path to be followed in VC setup message

### VC Identifiers and Forwarding Tables
- Packet contents
	- Virtual circuit identifier (VCI)
		- Label in PLS
	- Packet payload
-   How unique should VCIs be?
	- Globally unique (unrealistic)
	- Unique inside a given network
		- Coordination among routers necessary
	- Unique on a given interface
		- Easier to manage, no coordination required, but
		- VCI of a VC may change from link to link (e.g. MPLS and ATM)
- VC-specific information in forwarding table
	- Incoming interface, incoming VCI
	- Outgoing interface, outgoing VCI

### Example of Forwarding Tables (as in MPLS)
![[Pasted image 20251028134631.png]]
Watch it again lmao @ 30min gld 2_1

### Some More about MPLS
- Multiprotocol label switching (MPLS)
	- Switches packets over multiple layer-2 protocols
- Label switching router (LSR)
	- MPLS-enabled router
- Label switched path (LSP)
	- VC in MPLS
- MPLS mostly deployed in IP/MPLS environments
	- IP network serves as control plane for routing purposes
	- LSPs set up to forward data through IP network
- Benefits
	- Improved traffic engineering through explicit paths
	- Facilitates traffic measurement
	- Hides intermediate LSRs from unwanted IP control traffic
		- Such control traffic can be caused by user traffic
		- May be used for topology exploration
	- Simplified forwarding

### Labels in MPLS
![[Pasted image 20251028140109.png]]
- LSP setup
	- Signaling usually done over an IP network
	- Label Distribution Protocl (LDP)
		- Along IGP (Interior Gateway Protocol = IP routing protocol) shortest paths
	- Resource reSerVation Protocol - Traffic Engineering extensions (RSVP-TE)
		- Explicit routes possible
- Label stacking
	- "LSPs over LSPs"
	- LSP 2 spans 2 normal IP hops and LSP1
- Penultimate hop popping
	- Penultimate hop may already remove label: IP packet forwarded to dest
- 4-byte shim header
	- 20-bit label value
	- 3-bit traffic class
	- 1-bit indicates bottom of the stack
	- 8-bit TTL

## Internet Protocol

### Features of IP Communication
- IP implements datagram transmission mode
- Properties
	- Connecitonless
	- Unreliable
	- Packet-switched
	- Best effort service: as good as possible with available resources
- Design goal: end-to-end principle
	- Don't keep state information in intermediate systems
		- Resynchronization after failure not needed
		- No VC entries in routing tables
	- Flow-specific information stored only in end systems
		- E.g. TCP or application-specific connections
	- Separation of routing and forwarding

### IP Addressing
- Interfaces (IFs) are access points to Data Link Layer
- IP address
	- Identifies an IF of an IP node (host/router)
	- Hosts may have multiple IFs and IP addresses
	- Routers must have multiple IFs and IP addresses
- Encoding of 32 bits IP address
	- 10000110 00000010 00000010 00011101
	- Dot-decimal notation
		- 134.2.2.29

### Allocation of IP Addresses
- IP addresses are allocated en bloc (prefix allocation)
- Most addresses are allocated by Internet Assigned Numbers Authority (IANA) to
	- Regional Internet registries (RIRs)
	- RITs allocate them to local Internet Registries (LIRs) which are mostly Internet service providers
	- LIRs can further allocate them to other organizations and customers
	- RIRs also allocate AS (Autonomous System) numbers
- The 5 RIRs
	- Europe: RIPE Network Coordination Centre (RIPE NCC)
	- North-America: American Registry for Internet Numbers (ARIN)
	- Asia: Asia-Pacific Network Information Centre (APNIC)
	- South-America: Latin American and Caribbean Internet Addresses Registry (LACNIC)
	- Africa: African Network Information Centre (AfriNIC)

### Example: Naive IP Addressing withing an Organization
![[Pasted image 20251028141701.png]]
@45min gdi 2_1

### Subnetting
![[Pasted image 20251028142211.png]]
- Hierarchical addressing within a network
- Organization has network prefix for its network
- Partitions its network into smaller subnetworks
	- Assigns subnetwork prefixes out of the address space of network prefix
	- Hosts in the subnetwork have IP numbers starting with subnetwork prefix
- Parts of an IP address
	- Network prefix
	- Subnet ID
	- Host ID
- Example: ![[Pasted image 20251028142450.png]]

### Subnetwork Prefix
- All hosts on same subnetwork can locally exchange frames over the data link layer
	- Subnetwork prefix helps to identify hosts on same subnetwork
	- Reachability of all other subnetworks is given by the routing table
- Subnetwork address
	- Subnetwork prefix in bits followed by sufficient zeros, interpreted as IP address, e.g., 138.48.26.0 (Problem: how long is the prefix?)
- Subnetwork mask
	- Bit string indicating subnetwork prefix of an IP address with ones in dotted-decimal notation, e.g., 255.255.254.0 for subnetwork prefix length 23
- Subnetwork prefix
	- Address + subnetwork mask, e.g., 138.48.26.0 -> 255.255.254.0
	- CIDR notation, e.g., 138.48.26.0/23
- IP address on same subnetwork?![[Pasted image 20251028143042.png]]

### Example: IP Addressing with Subnetting
![[Pasted image 20251028143151.png]]
@57mins gdi 2_1

### Effect of Subnetting
- Benefits
	- IP addresses in the same local network represented by subnetwork prefix
		- Shorter routing/forwarding tables
		- New nodes can be added to local network without updating routing/forwarding tables
- Drawbacks
	- Most subnetworks are not fully occupied (waste of addresses)
		- More IP addresses needed than number of hosts

### Hierarchical Routing within ISPs
![[Pasted image 20251028143805.png]]
@01:04h gdi 2_1

### Unallocated Special Purpose IP Addresses
- 0.0.0.0
	- Used when a host is booting and does not yet know its address
- 127/8
	- Loopback addresses on each host, allows to reach servers on the local host
- 10.0.0.0/8, 172.16.0.0/12 and 192.168.0.0/16
	- Used for private networks (not directly attached to the Internet)
		- BELWUE-LAN: 10/8
		- Most home WLANs: 192.168/16
- 218.0.0.0/8 - 223.0.0.0/8 and 240.0.0.0/8 - 255.0.0.0/8
	- Reserved for future use
- 224.0.0.0/8 - 239.0.0.0/8
	- Used by IP multicast
- 255.255.255.255
	- Limited broadcast address, for own LAN, not forwarded by routers
- Let X.Y.0.0/16 be a subnet prefix
	- X.Y.255.255: direct broadcast address for the LAN, can be addressed from other networks