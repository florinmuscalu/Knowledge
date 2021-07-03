# Border Gateway Protocol (BGP)
- ## [Overview](#overview-1)
- ## [BGP Peers](#peers-1)
- ## [BGP Message Types](#messages-1)
- ## [Attributes](#attributes-1)
<br><br><br><br>
## <a name="overview-1"></a>**Overview**
- An **AS** is a set of routers that operate under the same administration.
- BGP is a classless routing protocol.
- Supports prefix routing.
- BGP peers must be connected directly for inter-AS routing.
- BGP version 4 is defined in **RFC 4271**.
- BGP is a path-vector routing protocol used for inter-domain routing.
    - uses an AS path, as a vector, to prevent inter-domain loops.
    - BGP routing information includes a series of AS numbers indicating the path that a route takes through the network.
    - BGP routing information includes the complete route to each destination.
    - BGP uses the routing information to maintain and information base of network layer reachability information (NLRI).
- BGP views the internet as a collection of Autonomous Systems (AS).
- Primarily used for inter-AS routing but also for MPLS-based VPNs or to separate large OSPF domains.
- BGP is normally used when a network has multiple upstream connections.
- **BGP uses TCP as its transport protocol (port 179)**.
## <a name="peers-1"></a>**BGP Peers**
- Peers can reside in the same of different ASs.
    - Peers in different ASs use the external session type (EBGP).
        - The connection between the two ASs consists of a physical connection and a BGP connection.
        - The physical connection is a shared data link laywer subnetwork between the two ASs.
        - The BGP connection exists between BGP speakers in each of the ASs.
        - **By default the EBGP connection is established between immediately connected devices located in two different ASs, because the TTL value of the EBGP packets is equal to 1.** The TTL can be increased by establishing a multihop BGP session.
    - Peers in the same AS use the internal session type (IBGP).
        - An IBGP connection is typically established between loopback interfaces of the routers not immediately connected. Loopback interfaces are used for stability reasons.
        - As BGP's TCP sessions are established using regular routing tables, and IGP is usually required inside the AS.
- BGP peering sessions are manually defined and rely on TCP sessions. **No automatic neighbor discovery**. 
- **BGP neighbor states**:
    - **Idle** state. The initial state when all incoming BGP connections are refused. A start event is required for the local system to initialize BGP resources and prepare for a transport connection with the other BGP peer.
    - **Connect** state. BGP is waiting for the transport protocol connection to be completed. If the transport protocol connection succeeds, the local system sends an **OPEN** message and transitions to the **OpenSent** state. If the connection fails, the local system restarts the ConnectRetryTimer, listens for a connection initiated by the remote BGP peer, and changes it's state to **Active**.
    - **Active** state. BGP is trying to aquire a peer by initiating a TCP connection. If the transport protocol connection succeeds, the local system sends an **OPEN** message and transitions to the **OpenSent** state. If it fails, you should check the physical connectivity and the configuration on both peers.
    - **OpenSent** state. BGP waits for an **OPEN** message from its peer. When this message is received, it checks for errors. If an error is found, the system trasitions back to **idle** state. If no errors are found, BGP sends a keepalive message.
    - **OpenConfirm** state. BGP waits for a **KEEPALIVE** or **NOTIFICATION** message. If no **KEEPALIVE** message is received before the negotiation timer expires, the local system sends out a **NOTIFICATION** message stating that the hold timer has expired and changes its state to **idle**. If a **NOTIFICATION** is received, it changes its state to **idle**. If a **KEEPALIVE** is received it changes state to **Established**.
    - **Established** state. BGP can exchange **UPDATE**, **NOTIFICATION** and **KEEPALIVE** messsages with its peer. When the local system receives and **UPDATE** or **KEEPALIVE** and when the negotiated hold timer value is nonzero, it restarts its hold timer. If the negotiated hold timer reaches 0, the local system sends out a **KEEPALIVE** message and restarts the hold timer.  
## <a name="messages-1"></a>**BGP Message Types**
- BGP messages are used to establish and maintain BGP peering sessions.
- All BGP messages use a commin header.
- BGP processes a message only after the entire message is received. Maximum message size is 4096 octets.
- The BGP header size is 19 octets.
- Message types:
    - **OPEN** message. Is sent once the TCP three-way handshake is complete. It initiates the BGP session and contains details about the BGP neighbor and information about supported and negotiated options.
    - **UPDATE** message. Used to transport routing information between peers.
        - An **UPDATE** message describes a single path and then multiple prefixes that can be reached through the same path.
        - BGP peers assume that this information is unchanged unless a subsequent update advertises a new path for a prefix or lists the prefix as unreachable.
        - If a neighbor goes down, the BGP speaker deletes all routes learned from that peer and updates its other peers accordingly.
    - **KEEPALIVE** message. Includes no data except for the header. Exchanged as needed to ensure the hold timer does not expire.
    - **NOTIFICATION** message. Used to signal that something is wrong. When an error is detected, the BGP session is closed. 
    - **REFRESH** message. Normally a BGP speaker cannot be made to readvertise routes that have been already sent and ACKd (using TCP). The route refresh message supports *soft clearing* of BGP sessions by allowing a peer to readvertise routes that havr already been sent.
## <a name="attributes-1"></a>**Attributes**
