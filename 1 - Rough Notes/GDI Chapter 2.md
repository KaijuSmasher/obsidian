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

### Principles of IP Forwarding
- Destination within local network
	- Next-hop: Destination
	- ![[Pasted image 20251028153139.png]]
- Destination outside local network
	- Next-hop: appropriate router
	- ![[Pasted image 20251028153205.png]]
- Forwarding table indicates for each destination (prefix)
	- Next-hop router (gateway) if IP destination is not in local network
		- Empty entry if destination attached to local network
	- IF to appropriate local network
- Encapsulate datagram in layer-2 frame with MAC address to next-hop
	- MAC address of next-hop taken from ARP (IPv4) or NDP (IPv6) table 
- Forward datagram over appropriate IF
- Example: ![[Pasted image 20251028153440.png]]
	@5min gdi 2_2
### Configuration Issues
- IFs including IP addresses with subnet mask
	- To determine directly connected subnets
- Default router: used to reach any unknown address
- Forwarding table (forwarding information base, FIB) contains
	- List of directly connected subnets including appropriate IF
	- List of reachable networks including appropriate next-hop
		- Manually configured or learned through routing protocols
	- Default route (0.0.0.0/0) with default router as next-hop
- Useful commands
	- Information about configuration (IP addresses, subnet masks, default router, DNS name,...)
		- Windows: ipconfig, Linux: ifconfig, ip (version 2.2 and higher)
	- Forwarding table
		- Windows: route print (route print -4), netstat -rn
		- Linux: route, ip route (version 2.2 and higher)

### Operations in IP Forwarding
- Check whether packet's destination address is one of the nodes's own addresses
	- If yes, packet reached destination
- Query FIB to look up the most specific route
	- Prefix A.B.C.D/M matches packet's destination address if
		- the M higher-order bits of destination address equal the M higher-order bits of A.B.C.D
	- Longest prefix match is most specific route
	- Tries (prefix trees, "information retrieval", optimized data structure) and caches may be used for efficiency reasons
- Forward packet along most specific route

### Example: Longest Prefix Matching
![[Pasted image 20251028154556.png]]
@13min gdi 2_2

### Mapping between IP and MAC Addresses
- MAC addresses needed for IP forwarding
	- MAC-IP mapping possibly not available in local ARP table
	- MAC-IP mapping needs to be found
- Address resolution protocol (ARP)
	- Source uses layer-2 broadcast to query all nodes on a subnet
	- whether one of them has a certain IP address
	- This node responds to source providing the desired MAC address
- IPv6 uses neighbor discovery protocol (NDP) and NDP table instead of ARP and ARP table

### Address Resolution Protocol (ARP)
![[Pasted image 20251028155206.png]]
@19min 2_2

### Persistence of Data in ARP Table
- When should a host send ARP requests?
	- Before sending each IP packet?
		- No, each host/router maintains an ARP table that contains the mapping between IP addresses and ethernet addresses
		- An ARP request is only sent when the ARP table is empty
- How to deal with hosts that change their addresses?
	- Expiration timer is associated with each entry in the ARP table
		- Entry in ARP table is removed upon timer expiration
		- Some implementations send an ARP request to revalidate entry before removing it
		- Some implementations remember when ARP entries have been used to avoid removing an important entry
- Useful commands to show ARP table
	- Windows: arp -a
	- Linux: arp, ip neigh (version 2.2 and higher)

### Proxy ARP
![[Pasted image 20251028155635.png]]
- Special setting
	- Router connects two layer-2 networks A and B that utilize the same IP address range
- Proxy ARP
	- Router answers ARP requests from one network (A) for hosts in the other network (B)
	- Future traffic from one network (A) will be sent to the router which forwards it to the host in the other network (B)
- How to recognize Proxy ARP?
	- ARP cache for hosts in one network has identical MAC addresses for all hosts in the other network (B)
	- May also be a sign for ARP spoofing (ARP request poisoning)
		- Good for man-in-the-middle attacks

### Man-in-the-Middle (MitM) Attack
![[Pasted image 20251028160036.png]]
@24min 2_2

### Reverse ARP (RARP)
- Problem
	- Hosts knows its MAC address but not its IP address after booting
	- How does a host learn its IP address?
- Solution
	- Server-based autoconfiguration based on RARP
	- RARP server holds table with manually configured pairs (MAC address, IP address)
	- Hosts broadcasts layer-2 frame with RARP request
	- RARP server responds layer-2 frame with RARP reply containing the requested IP address
	- Mainly used for limited terminals that boot from a remote server
- RARP does not provide
	- Subnet mask
	- Default router
	- DNS server

### Dynamic Host Configuration Protocol (DHCP)
- Objective
	- Automatic integration of hosts in an IP network
	- More powerful alternative to RARP
- Operation
	- When host attaches to a subnet, it sends a DHCPDISCOVER via IP-broadcast to find DHCP server or relay (source IP:0.0.0.0)
	- DHCP server/relay replies with DHCPOFFER via IP broadcast (includes IP addresses)
	- Host can pick IP address and respond with DHCPREQUEST via IP broadcast
	- DHCP server allocates an IP address for some time period and can also provide additional information in DHCPACK (subnet, default router, DNS server, domain name, static routing table entries, NTP server, ...) via IP-broadcast
	- DHCP servers can be configured to always provide the same IP address to a given end host
	- Host reconfirms its allocation regularly or releases IP address with DHCPRELEASE

### IP Multicast
- Multicast group
	- Addressable with a special IP address (224.0.0.0/8)
	- Nodes can join and leave
	- Messages sent to this group are distributed over a multicast tree to all group members
	- Sender of a message does not need to
		- Know all group members
		- Transmit a message more than once
	- Used by T-Home Entertainment
- Implementation in the Internet
	- IGMP
		- Allows a host to join or leave a multicast group
		- Communication between host and its router
	- Multicast routing protocols
		- Establish multicast trees among routers participating in a multicast group
		- Examples
			- Protocol-independent multicast (PIM)
			- Distance-vector multicast routing protocol (DVMRP)

### Internet Group Management Protocol (IGMP)
 - For communication between host and router
 - Router
	 - Maintains list of hosts that belong to a multicast group
	 - Forwards traffic of that group to these hosts
- IGMP used to manage memberships
- Router sends "membership-queries" in regular intervals (default 125s)
- hosts respond with "membership-reports" = indication of the multicast groups they want to participate in
- Router receives "membership-report" from hosts and adds them to its local membership lists for multicast groups
- Membership is soft state
	- Requires regular refresh through "membership-reports" from host
	- Automatic membership cancellation if host does not answer anymore
- Host can also send
	- membership-report to router instead of waiting for a membership-query by a router and answering with a membership-report -> faster subscription
	- leave-group to leave group faster than timeout for soft state expiration -> faster cancellation

## IPv4 - packet format and mechanisms

### IP Header Format
 ![[Pasted image 20251028162214.png]]

### Protocol Numbers: Examples
![[Pasted image 20251028162249.png]]

### Handling of Transient and Permanent Loops
- Problems 
	- Loops can occur in an IP network
		- Permanent loops due to configuration errors
		- Transient loops while routing tables are being updated
- Solution
	- Each packet contains a Time-to-live (TTL) that indicates the maximum number of intermediate routers that the packet can cross
		- Many hosts set the initial TTL of their packets to 32 or 64
	- Each router checks the TTL of all packets
		- IF TTL=1, packets is discarded and source is notified via ICMP
		- IF TTL>1, TTL is decremented by at least 1 and packet is forwarded
	- Use of TTL is a means to bound the lifetime of packets inside the Internet

### Dealing with Limited MTU: Fragmentation
- MTU
	- Maximum transfer unit
	- Maximum packet size in a subnet
	- Larger packets cannot be forwarded
		- Although IP packets can basically be up to 64 Kbytes large
- IP packet fragmentation (only IPv4)
	- Routers fragment packets if
		- Packet size exceeds MTU
		- DF-bit set to 0
	- Uses Identification, MF-bit, FragmentOffset
	- Destination reassembles fragments
	- Burdens routers, possibly repeated fragmentation needed
	- More details in Übung
- ![[Pasted image 20251028162818.png]]

### Dealing with Limited MTU: Path MTU Discovery
- Used in IPv4 and IPv6 to avoid fragmentation
- Mechanism
	- Source sends maximum size packet (local MTU)
	- DF-bit set to 1 (don't fragment)
	- Intermediate router with lower MTU possibly drops packet and returns an ICMP (error) message including appropriate MTU
	- Source tries again with lower MTU
- ![[Pasted image 20251028163001.png]]

### Typical Distribution of IP Packet Sizes
- Mean packet size: ~ 350 Bytes
- Most frequent packet sizes
	- 40 Byte: ~40%
	- 44 Byte: ~6%
	- 522 Byte: ~10%
	- 576 Byte: ~5%
	- 1500 Byte: ~12%
- Small pkts mostly for TCP acknowledgement
- Most data carried in 1500 bytes pkts
- Voice over IP hardly visible
- ![[Pasted image 20251028163219.png]]

### Detection of Transmission Errors
- Transmission error inside IP packet header can cause problems
	- Example : error in source or destination IP address
- IP uses a checksum to detect transmission errors in header
	- Each router or end host verifies checksum of all received packets
	- Packets with erroneous header are immediately discarded
	- 16 bits checksum (same as TCP/UDP) computed only over header fields
		- Header checksum assumed zeros for calculation
		- One's complement addition with inversion in the end
		- Advantage: simple to update when TTL is decremented
		- See lecture "Informatik der Systeme" for details
- Transmission error inside IP packet Payload
	- Some applications may continue to work despite such an error
	- IP: no detection of transmission errors in packet payload

### IP Options
- Constraint: maximum header size including options is 64 bytes
- Sample IP header options
	- Strict source route option
		- Allows the source to list IP addresses of all intermediate routers to reach destination between source and destination
	- Loose source route option
		- Allows the source to list IP addresses of some intermediate routers to reach destination between source and destination
	- Record route option
		- Allows each router to insert its IP address in the header
		- Rarely used because limited header length
	- Internet timestamp option
		- List of timestamps (4 octets) when packet reaches router, or record route plus timestamps, or loose source route plus timestamps
		- For measurement purposes
	- Router alter
		- Allows the source to indicate to routers that there is something special to be done when processing this packet

### Strict and Loose Source Routing
![[Pasted image 20251028164045.png]]
@55mins 2_2

### Handling of Transmission Errors
- Routers/hosts check headers of received packets
	- Header length, IP version number, datagram length, checksum, TTL, protocol number
- What should a router/host do when it receives an erroneous packet
	- Packet whose destination is not the current end host
	- Packet containing a header with invalid syntax
	- Packet received with TTL=1
	- Packet destined to protocol not supported by host
- Solution
	- Ignore and discard the erroneous packet
	- Inform the packet's source about the problem with an ICMP message
		- ICMP: Internet Control Message Protocol (TFC792)
		- ICMP messages sent inside IP packets by routers (mainly) and hosts
		- To avoid performance problems, most hosts/routers limit the rate of ICMP messages that they send

### Use Cases for ICMP Messages
- Error in the IP header
	- Parameter problem
		- Incorrect format of IP packet
	- TTL exceeded
		- Router received packet with TTL=1
		- Used by traceroute
	- Fragmentation
		- The packet should have been fragmented, but its DF flag was true
- Check for liveness
	- Echo request / echo reply
		- Used by ping
- Routing error, destination unreachable
	- Final destination of packet cannot be reached
		- Entire subnet unreachable
		- Individual host unreachable within a reachable subnet
		- protocol/port unreachable on a reachable host
	- Redirect
		- The packet was sent to an incorrect first-hop router and should have been instead sent to another first-hop router whose address is provided

### ICMP Messages
![[Pasted image 20251028164748.png]]
@1:03h 2_2

### Overview of TCP/IP-Related Protocols (IPv4)
![[Pasted image 20251028164829.png]]
@1:04 2_2

###  The TCP/IP Protocol Family
- TCP/IP often used as synonym for the entire protocol family
- Classification of protocols within the ISO/OSI reference model
- The control protocols ICMP and IGMP utilize the IP service but are classified as part of the network layer due to their function
- ARP and RARP do not exchange OP packets but send their messages on the link layer. However, their function contributes to the network layer
- DHCP messages are carried over UDP
- ![[Pasted image 20251028165142.png]]

## IPv6 - packet format and mechanisms

### Main Driver for IPv6: Address Shortage
- 32-bit IPv4 address space too small
	- Late 1980s: exponential growth of Internet
	- 1992
		- Most class B networks will soon be assigned
		- Networking experts warn that IPv4 address space could become exhausted
	- 3.2.2011: IANA allocates last /8 IPv4 blocks to RIRs
- Short term solutions
	- 1993: classless interdomain routing (CIDR), more later
	- Network address translation (NAT), causes other problems, more later
- Long term solution: IPv6 with longer addresses

### Additional Issues
- Implementation issues - 1990s
	- IPv4 packet format is complex
	- IP forwarding is difficult in hardware
- Missing functions - 1990s
	- IPv4 requires lots of manual configuration
		- Competing protocols already supported autoconfiguration in 1990s
		- Connectionless Networking Protocol CLNP, Appletalk, IPX, ...
	- How to Support Quality of Service in IP?
		- Integrated Services and Differentiated Services did not exist then 
	- How to better support security in IP?
		- Security problems started to appear but were less important than today
	- How to better support mobility in IP?
		- GSM started to appear and some were dreaming of mobile devices attached to the Internet

### IPv6 Addresses
![[Pasted image 20251028165932.png]]

### Representation of 128 Bits IPv6 Addresses
- Hexadecimal format
	- Example: FEDC:BA98:7654:3210:FEDC:BA98:7654:3210
	- Some IPv6 addresses contain lots of zeros
- Compact hexadecimal format
	- Leading zero compression
		- Drop leading zeroes in any 16-bit field, but at least one number must remain
		- Example: :0: :80: :800: :8000: :db8:
	- Zero compression
		- Use "::" to indicate one or more groups of 16 bits of zeros
		- The "::" can only appear once in an address
		- Examples:![[Pasted image 20251028170211.png]]

### Three Types of IPv6 Addresses
- Unicast addresses
	- An identifier for a single interface
	- A packet sent to a unicast address is delivered to the interface identified by that address
	- Special addresses ![[Pasted image 20251028170303.png]]
- Anycast addresses
	- An identifier for a set of interfaces
	- A packet sent to an anycast address is delivered to the "nearest" one of the interfaces identified by that address
- Multicast addresses
	- An identifier for a set of interfaces
	- A packet sent to a multicast address is delivered to all interfaces identified by that address

### Allocation of IPv6 Addresses
- IANA assigns blocks of IP addresses to Regional Internet Registries (RIR)
- IP address consists of 64 bit prefix and 64 it interface ID
	- The latter is function of MAC address or randomly generated (RFC4941)
- An organization can be allocated two different types of IPv6 addresses
	- Provider Independent (PI) addresses
		- usually allocated to ISPs or very large enterprises directly by RIRs
		- Default size is /32
	- Provider Aggregateable (PA) addresses
		- Longer prefixes, assigned by ISPs from their PI block
			- /48 in the general case, except for very large subscribers
			- /64 when one and only one subnet is needed by design
			- /128 when it is absolutely known that one and only one device is connected
- ![[Pasted image 20251028170841.png]]

### Global Unicast Addresses
- IPv4 mapped IPv6 addresses
	- 0:0:0:0:0:ffff::/96 (80 0-bits, followed by 16 1-bits)
	- Last 32 bits contain IPv4 addresses
	- Appropriate routers can convert between IPv4 and IPv6 addresses
- IANA-assigned addresses
	- 2000::/3 (2000:... to 3fff...)
	- 2001 provider-assigned addresses, may be further delegated to customers
	- Interworking mechanisms
		- 2001::/32 (2001:0:...) used for Teredo
		- 2002 6to4 addresses
	- 2001:db8::/32 Example addresses for documentation only
- ![[Pasted image 20251028171207.png]]

### IPv6 Link-Local Addresses
![[Pasted image 20251028171402.png]]

### Unique Local Addresses (ULA)
- fc00::/7
	- Unicast
	- Contain a 40-bit random number in the routing prefix
		- To prevent collisions when two private networks are interconnected
	- Despite being inherently local in usage, the IPv6 address scopes of unique local addresses is global

### IPv6 Multicast Addresses
![[Pasted image 20251028171610.png]]

