# lec1

## abbreviations

1. **RFC** Request for comment
2. **IETF** Internet engineering task force
3. **ISP** Internet service provider
4. **IXP** Internet exchange point
5. **WWW** World wide web : application of the internet
6. **URL** Uniform resource locator
   - 17 message.
     - 6 to find ip
     - 3 for connection established for tcp
     - 4 for HTTP request
     - 4 for tearing down TCP
7. **HTTP** Hyper Text transfer protocol
8. **TCP** Transmission Control Protocol
9. **LAN** Local area network < 1Km
10. **WAN** Wide Area Network - WorldWide
11. **MAN** metropolitan Area network - < 10km
12. **SAN** System area network - ROOM
13. **MAC** Media Access Control
14. **S-TDM** Synchronous Time Division Multiplexing
15. **S-FDM** Synchronous Frequency Division Multiplexing
16. **IP** Internet protocol
17. **RRP** request/reply protocol
18. **MSP** message stream protocol
19. **HHP** host to host protocol
20. **OSI** Open systems interconnections
21. **TCP/IP** Transmission control protocol/Internet protocol
22. **UDP** User dataGram Protocol
23. **RTT** Round trip time
24. **BISYNC** Binary Synchronous Communication
25. **STX** start of text
26. **ETX** end of text
27. **DLE** Data Link Escape
28. **PPP** point to point protocol
    - run over internet access link
29. **NCP** Network Control Protocol
30. **LCP** Link Control Protocol
    - Used in PPP
31. **DDCMP** Digital data communication protocol
    - used in DECnet
32. **HDLC** High level Data link Control
    - uses bit oriented
33. **EDC/ECC** Error detection code/error correction code
    1. Two dimentional parity
       - Used by _BISYNC_ when transmitting ASCII
    2. CRC
    3. Internal CheckSum
34. **CRC** Cyclic Redundancy check
35. **FEC** forward error correction
36. **ARQ** Automatic Repeat Request
    - Stop and wait
    - Sliding Window
    - Concurrent logical channel
37. **CSMA/CD** Carrier sense multiple access with collision detection
38. **TDMA** Time division multiple access
39. **IBBS** Independent Basic Service Set
40. **AP** Access Point
41. **BBS** Basic service sets
42. **OFDM** orthogonal Frequency Division multiplexing
43. **WI-FI** wireless fidelity
44. **RTS** request to sent
45. **CLS** clear to send
46. **DSLAM** digital subscriber line access multiplexer
47. **DSL** Digital subscriber line

## definitions

1. **Computer networks** set of interconnected autonomous components
2. **Components**
   1. nodes/hosts : source/destination of data > laptops desktops
   2. intermediate / cooperating nodes : relaying on data among connected hosts > switch, hub ,router
   3. links : transmitting data between two adjacent nodes
3. **packet switched networks** : it implies the strategy of store and forward, **it's more efficient for computer network**
4. **circuit switched network** : first stablish a dedicated circuit across a sequence of links and thn allow the source node to send a stream of bits across this circuit to a destination
5. **addressing** : a mechanism of specifying and allocating a byte string that uniquely identifies a node or set of nodes
6. **ٌRouting** : process of determining systematically how to forward a packet towards a distinction based on it's address
7. **Router / Gateway** : a node specialized to connect two or more network
8. **Broad cast communication networks** : information transmitted by one node is received by other nodes in the network **_like_** Ethernet LAN
9. **Switched Communication network** : information transmitted to a set of designated nodes **_like_** WANs (Telephony Network, internet)
10. **Deterministic Multiplexing** : TDM/FDM the link is divided into slots (time or frequency ) and each node and send data in it's shred resource at any time but While a sender has no data to send, its share of resource (time slot,
    or frequency band) remains idle and idle resource cannot be used by other senders **_not suitable for computer communications_**
11. **Statistical Multiplexing** : Data is send on demand of each flow - flow can be packet or entire message - we can use **fifo** _First in first out_ or **Round-Robin** _each has round to send and if it hasn't data skipped_ and **Priority queue**
    - The source node may need to fragment the message into several packets, with the receiver reassembling the packets back - A switch becomes
    - Congested when it receives packets faster than the shared link can accommodate.
    - Appropriate to burst computer communications
    - Efficient network resource utilization
12. **Internet** : World wide publicly accessible network of interconnected computer network that transmit data using packet switched using internet protocol
13. **Modularization** : divide the whole system into a small and less complex blocks of different functionalities, these blocks are united with a well defined interface hid the complexity of block behind it
14. **Abstraction** : The act of hide implementation details behind a well defined interface, it's a fundamental tool used by system designers to manage complexity
15. **Layering** : Organize a network system into a succession of logically distinct entities, the service provided by one entity is solely based on the service provided by the lower level entity
    - _Modularity_ : easy to manage and maintain
    - _Reuse_ : upper layers can reuse the functionalities provide by th lower layer
    - _Abstract functionality_ : lower layer can changed without affecting the upper layer
16. **Entities** : Abstract object that mak up the layers of network system, provide communication services to upper layer entities by calling the communication services provided by the lower layer entities
17. **Protocol** : Specification of rules that are required for communication between two or more entities, protocols defines the interface between the layers in the same system and with the layers in the peer system
    - Each protocol object has two different interfaces
      - service interface
      - peer to peer interface
    - communication activities that governs b protocol
      - Format, order of messages sent and received among entities
      - Actions taken on messages
      - service interface to the upper layer
18. **Encapsulation** : by this approach protocol can carry control information to instruct its peer how to handle received data
19. **Header/trailer** : small data structure attached at the sender and detached at the receiver used among peer for communication with each other
20. **Network Architecture** : set of rules governing the form and content of an entity graph of network _like_ OSI model, network architecture, its a design a blueprint on how to organize the implementations of the computer network
21. **Bandwidth** the number of bits that can be transmitted over the network in a certain period of time
22. **Latency** : corresponding to how long a message takes to travel from one end to other
23. **RTT** corresponding to how long a message takes to travel from one end to other and back again
24. **Throughput** : the rate at which bits are transferred between sender and receiver
25. **Jitter** Variance in latency
26. **Delay \* BandWidthProduct** how many bits the sender can transmit before the first bit arrives at the receiver if the sender keeps the pipe full
27. **Network Adaptor** piece of hardware that connects a node to a link. it contains a signaling component that actually encodes bits into signals at the sending node and decodes signal into bits at the receiving node
28. **Baud rate** the rate at which the signal changes
29. **Byte oriented** View each frame as a collection of bytes rather than a collection of bits
30. **Bit Oriented** View the frame as a collection of bits rather than a collection of bytes
31. **Byte Stuffing** if any of sentinel characters appears in data we add _DLE_ parameter before it
32. **Bit stuffing** when transmitting five consecutive 1s insert 0 before transmitting the next bit
    - at receiver if received five consecutive 1s
      - next bi = 0 ? remove it
      - next bit is 1 ?
        - next bit is 0 ? the frame ends
        - next bit = 1 ? error
33. **Acknowledgment** a small control frame (header without data) that a protocol sends back to it's peer saying it has received an earlier frame
34. **Timeout** the action of waiting a reasonable amount of time
35. **Multiple access** a set of hosts can send and receive frames over a shared network, a frame sent by host is received by all other hosts but accepted by the intended host(s)
36. **MAC** distributed algorithm running on the nodes determine how thy can share the channel, when they can transmit frames
37. **Channel partitioning** divide the channel into small pieces (time slots, frequency, code) and allocate piece to node for exclusive use _like_ FDMA , TDMA
38. **Random access** Channel nor divided just allow collision and recover from collision _like_ ALOHA, CSMA, CSMA/CA, and CSMA/CD
39. **Take turns** nodes take turns to send, but nodes with more data can take longer turns _like_ bluetooth, token ring, FDDI
40. **CSMA/CD**
    1. **Carrier sense** means that the node can destingush between idle and busy link
    2. **multiple access** means that set of nodes can send and receive ove ra shared link
    3. **Collision detection** means that the node can listen while transmit so it can detect when the frame is collided with other frame
41. **Repeater** device used to forward digital signals much like amplifier in forwarding analog signals
42. **HUB** multiple variant repeater
43. **Transceiver** A small device attached to the tp of ethernet, detects if the line is idle and drive the outgoing signals and receive the incoming signals
44. **Terminator** attached to the end of each segment to absorb the signal and keep it from bouncing back
45.

## Resource Sharing

1. Multiplexing
2. De-multiplexing
3. Synchronous Time-Division Multiplexing
   1. Time slots/data transmitted in predetermined slots

## A Taxonomy of Communication Networks

- Communication network
  - BroadCast Communication Network
  - Switched Communication network
    - Circuit-Switched Communication Network
    - Packet-Switched Communication network
      - DataGram Network
      - Virtual Circuit network

## OSI Architecture

1. Application layer
   - the service provided to the end user
2. Presentation layer
   - format of data exchange between peers
3. session layer
   - handle things like in long time transfer
     - session management
     - access control
     - synchronization
4. Transport layer
   - implement process to process channel
   - unit of data called message
5. network layer
   - handle te routing between nodes within packet switched network
   - the unit of data called packet
6. Data link layer
   - collets a stream of bits into a large aggregate called frame
7. Physical layer

   - handle the transmission of row of bits aver the communications link

**The transport layer and the higher layers typically run only on end hosts and not on the intermediate switches and route**

## internet architecture

- Doesn't implies strinct layering
  - you can bypass the transport layer ang go directly to ip protocol
- An hour glass shape
  - narrow at the middle at the ip protocol and wide at top and bottom
- in order to add new protocol, to be officially included thee's must be both protocol specification and at least one representative implementation for thi specification
- Four layer
  - Application layer
    - the service provided to the end user and implies http, ftp, telnet and other applications protocols
  - Transport layer
    - process to process channel
    - TCP : reliable byte stream channel
    - UDP : unreliable dataGram delivery channel
  - Internet layer
    - host to host packet transition
    - inl ip protocol
  - Network Access layer

## 5-Layered Network Architecture

1. Application
2. Transport
3. Network
4. Data link
5. Physical

## Source of delay

1. Nodal processing
   1. time consumed while check bit error
   2. determining the output link
   3. **Usually Omitted**
2. Queueing
   1. waiting for output link to transmission
   2. depends on the congestion level
   3. **Usually Omitted**
3. transmission delay
   - = packet length / link width
   - **Effective when large byte transmission**
4. Propagation delay
   - = link length / speed of light
   - **Effective when One bit transmission**
5. Throughput
   - Throughput = transfer size / Transfer time
   - Transfer Time = RTT + transfer size / BandWidth

## network connectivity

1. Direct
   - hosts directly connected via physical medium or logical channel
     1. Point to point :
     2. Multiple access
2. InDirect
   - switched
   - interconnection of network

## proplems of connecting a network

1. physical medium to make connection
2. Encoding : How to encode and decode binary data over the link between sender and receiver
3. Framing : determining the beginning and end of a frame
4. Error detection : how to detect possible errors
5. Reliable transfer : how to make frame transmission more reliable
6. media access control : mediate access to share link between multiple hosts

## framing

- byte oriented
  - Sentinel
    - flag 8
    - Address 8
    - Control 8
    - Protocol 16
    - payload
    - Checksum 16
    - flag 8
  - Byte-Counting
    - SYN 8
    - SYN 8
    - Classes 8
    - Count 14
      - donates the number of bytes
    - Header 42
    - Body
    - CRC 16
- Bit Oriented
  - HDLC
    - Beginning sequence
      - 0x7E
    - Header
    - Body
    - CRC
    - Ending Sequence

### Link type

1. Wireless LAN _low_
2. Satalitte _middle_
3. Cross-Country fiber _high_

   **Common services available for the last-mile connection**
   **_DSL(copper)_** < **_G.FAST(copper)_** < **_PON(optical)_**
