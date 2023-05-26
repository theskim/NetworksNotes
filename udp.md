# UDP (User Datagram Protocol)

- UDP is a transport layer protocol in the OSI model.
- It provides connectionless, unreliable communication between devices.
- UDP is a simple, lightweight protocol that prioritizes low latency over reliability.

**Key Features:**

- **Connectionless:** UDP does not establish a connection before transmitting data. Each datagram is treated independently.
- **Unreliable:** UDP does not guarantee delivery or ensure data integrity. It does not provide acknowledgments or retransmissions.
- **Low Overhead:** UDP has minimal protocol overhead, making it suitable for applications that prioritize speed and low latency.
- **No Flow Control:** UDP does not perform flow control mechanisms to manage the rate of data transmission.
- **No Congestion Control:** UDP does not monitor or adjust transmission rates based on network congestion.

**Advantages of UDP:**

- **Low Latency:** UDP offers faster transmission as there is no need for establishing connections and performing reliability checks.
- **Minimal Overhead:** UDP has a smaller header size compared to TCP, resulting in less network overhead.
- **Broadcast and Multicast Support:** UDP allows sending data to multiple devices simultaneously using broadcast or multicast.

**Use Cases:**

- **Real-time Applications:** UDP is commonly used in real-time applications such as VoIP, video streaming, online gaming, where low latency is critical.
- **DNS (Domain Name System):** DNS queries and responses are often sent using UDP due to their small size and low overhead.
- **DHCP (Dynamic Host Configuration Protocol):** DHCP uses UDP for IP address assignment to devices on a network.

Although UDP lacks reliability compared to TCP, its speed and low overhead make it suitable for applications where real-time data delivery and low latency are prioritized.
