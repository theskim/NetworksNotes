# TCP (Transmission Control Protocol)

- TCP is a transport layer protocol in the OSI model.
- It provides reliable, connection-oriented communication between devices.
- TCP ensures error-free, ordered, and congestion-controlled data transmission.

**Key Features:**

- **Reliability:** TCP guarantees the reliable delivery of data by implementing acknowledgments, retransmissions, and error detection.
- **Connection-oriented:** TCP establishes a connection between sender and receiver before data transmission and ensures reliable data transfer.
- **Ordered Delivery:** TCP delivers data packets in the same order they were sent to ensure the integrity of the transmitted information.
- **Flow Control:** TCP implements flow control mechanisms to manage the rate of data transmission based on the receiver's ability to handle it.
- **Congestion Control:** TCP monitors network congestion and adjusts its transmission rate to avoid overwhelming the network.
- **Full-Duplex Communication:** TCP allows simultaneous bidirectional data flow between sender and receiver.

**TCP Handshake:**

1. **SYN:** The initiating device sends a SYN packet to the receiving device to request a connection.
2. **SYN-ACK:** The receiving device responds with a SYN-ACK packet, acknowledging the request and providing its own SYN value.
3. **ACK:** The initiating device sends an ACK packet to confirm the connection and synchronization.

**TCP Connection Termination:**

1. **FIN:** One device initiates the connection termination by sending a FIN packet.
2. **ACK:** The receiving device acknowledges the FIN packet.
3. **FIN:** The receiving device also sends a FIN packet to initiate its connection termination.
4. **ACK:** The initiating device acknowledges the second FIN packet.

TCP is widely used in applications that require reliable and ordered delivery of data, such as web browsing, file transfer, email, and other network services.
