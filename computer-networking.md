### [Computer Networking](/computer-networking.md)
-- *James Kurose, Keith Ross*


- **Circuit switching** vs **Packet switching** - pre vs on-demand link resource allocation
   - aka statistical multiplexing
- **Channel partitioning protocol categories:** **FDM** vs **TDM** vs **CDM**
- **Delays:** processing, queuing, transmission, propagation, packetization (VoIP)
- **Packet types:** message, segment, datagram, frame

- **Application Architecture:** **client-server** or **P2P**
- **Socket** - interface between the app layer and the transport layer; aka API
- **Multimedia** apps are delay and jitter sensitive but loss-tolerant
- **Elastic** apps are delay-tolerant but loss-sensitive

- **Protocol Characteristics:**
  - **connection-oriented** vs **connectionless service** (TCP vs UDP)
  - **stateful** vs **stateless** (BGP, FTP, RTSP vs HTTP)
  - **persistent** vs **non-persistent** connections
  - **in-band** vs **out-of** band control connection (HTTP vs FTP, RTSP, SIP)
  - **pull** vs **push** (HTTP vs SMTP)

*****

- **ARQ** (Automatic Repeat reQuest) protocols capabilities:
  - error detection - timeout
  - receiver feedback - ack
  - retransmission

- **TCP**
  - **Flow Control** - speed-matching service to ensure sender doesn't overflow receiver's buffer by using the receive window (rwnd)
  - **Congestion Control** - throttling the sender due to congestion within the network by using the congestion window (cwnd)
    - **AIMD** (Additive Increase Multiplicative Decrease) - saw tooth behavior

*****

- Network layer can provide:
   - connection service using virtual-circuits (VCs)
      - maintain connection state using signaling messages
      - 3 phases: VC setup, data transfer, VC teardown
   - connectionless service aka datagram networks (IP)
   
- Router components: input ports, switching fabric, output ports, routing processor
- Router functions: route propagation and forwarding path computation
- Packet scheduler:
   - at the output port, chooses one packet among those queued for transmission
   - plays a crucial role in providing QoS

- Routing algorithm classificaton:
   - **Adaptive** vs **Oblivious** (routing decisions based on network state (load, conggestion))
   - **Global** vs **Decentralized**; aka link-state vs distance-vector
   - **Static** vs **Dynamic**
   - **Intra-AS** vs **Inter-AS**

- Network link types:
   - **Point-to-Point**: PPP, HDLC
   - **Broadcast**: Ethernet

*****

- Wireless network types:
   - infrastructure-based single-hop (**WiFi**) or multi-hop (**Mesh**)
   - infrstructure-less single-hop (**bluetooth**) or multi-hop (**MANET**)

- Handoff - mobile client moving from beyond the range of one AP into the range of another AP

- Mobility management principles:
   - home network, home agent, permanent address
   - foreign network, foreign agent, COA (Care-of Address)

*****

- Multimedia application classes:
   - streaming stored audio/video
   - streaming live audio/video
   - real-time interactive audio/video

- **PCM** (Pulse Code Modulation) - speech encoding technique with a sampling rate of 8k samples per second and 8 bits per sample, giving a rate of 64 kbps

- Multimedia protocols:
   - **RTSP** - network control protocol used for establishing and controlling media sessions between endpoints
   - **RTP** - used for carrying audio and video media streams
   - **RTCP** - provides out-of-band statistics and control info for RTP
   - **SIP** - used for session establishment/management; works with RTP or UDP
   - **H.323** - similar to SIP but more complex

*****

- **Scheduling mechanisms:** FIFO, priority queueing, WFQ
- **Policing mechanisms:** criteria: average rate, peak rate, burst size

- **DiffServ** - service differentiation based on traffic classes; elements:
   - Edge functions: packet classification and traffic conditioning
      - traffic profile uses a meter to classify, mark and shape/drop packets
   - Core function: forwarding
      - **PHB** - different performance based on packet markings
         - **EF** - guaranteed to receive enough bandwidth to meet configured rate
         - **AF** - divides traffic into 4 classes, each with 3 drop preferences

- **IntServ** - provides QoS guarantees to individual application sessions
   - uses **RSVP** to install soft-state in routers using call setup signaling
   - not widely used

*****

- Properties of secure communication:
   - **Confidentiality**, **Endpoint Authentication**, **Message Integrity**

- **Encryption** - provides confidentiality by keeping data private
   - **Symmetric Encryption**
      - has fundamental problem of key distribution
      - Cipher classes: **stream ciphers** and **block ciphers** (**AES**)
   - **Public Key Cryptography** - asymmetric encryption
      - **Diffie-Helman** - one of the first algorithms
      - **RSA** - popular public key cryptography algorithm
 
- **Hash Function** takes an input and computes a fixed-length string
   - it is computationally infeasible to find the input from the output
   - **MD5** and **SHA** hash algorithms are widely used

- **MAC** performs message intergrity using hash functions with a shared key
   - does not require an encryption algorithm
   - **HMAC** is a popular standard and works with MD5 or SHA

- **Digital Dignatures** - provide peer authentication, message integrity and non-repudiation
   - provides similar services as MAC but requires PKI
   - sender encrypts message's hash using his private key (aka signs it)

- **PKI**
   - Public key certification - verifying that a public key belongs to a specific entity
   - **CA** - binds a public key to a particular entity, validates identities and issues certs
   - **Digital Certificate** contains owner's public key and unique info
      - is signed by the CA

- **SSL/TLS** secures TCP by providing: confidentiality, data integrity, client/server authentication
   - provides TCP's services to applications enhanced with security services

- **IPSec** protocol suite provides security at the network layer
   - **AH** protocol provides authentication and data integrity (51)
   - **ESP** protocol provides authentication, data integrity and confidentiality (50)
   - **Transport mode** or **Tunnel mode** (more popular)
   - **SA** - network layer unidirectional logical connection
   - **IKE** - automated mechanism for creating SAs

- Firewall categories: packet filters, stateful filters, application gateways
- DoS attack categories: vulnerability attack, bandwidth flooding, connection flooding

*****

- Network management areas: performance, fault, configuration, security, accounting
- Network management architecture components: manager (NMS), managed devices, agent (SNMP software)
- **SNMP** - network management protocol used for conveying information and commands between the manager and an agent executing on behalf of that entity within a managed network device
   - request-response mode to query or modify **MIB** object values or unsolicited **trap messages** from the agents to the manager