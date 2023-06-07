# WebSocket

WebSocket is a communication protocol that provides full-duplex, real-time communication between a client (typically a web browser) and a server. It is part of the HTML5 specification and is designed to overcome the limitations of HTTP, which is stateless and essentially half-duplex. Unlike HTTP, WebSocket supports full-duplex communication, meaning data can be sent and received simultaneously.

- **Full-duplex**: Both the client and the server can send and receive data at the same time. This allows real-time interaction between the client and the server.
- **Persistent connection**: Once established, the WebSocket connection remains open, allowing continuous data transfer. This is unlike HTTP where each request-response pair requires a new connection.
- **Lower overhead**: WebSocket messages don't require additional metadata (headers) after the connection is established, leading to reduced data overhead compared to HTTP, where each request and response carries headers.

## WebSocket Setup Process
The WebSocket connection is established through a handshake process:
1. The client initiates a WebSocket connection using the WebSocket handshake protocol. This request is sent to the server as a standard HTTP request with a specific header ("Upgrade: websocket"), indicating the client's desire to establish a WebSocket connection.
2. The server responds to the client's request with an HTTP response that includes a "101 Switching Protocols" status code. This response confirms the server's agreement to upgrade the connection from HTTP to WebSocket.
3. Once the handshake process is completed, the connection is upgraded from HTTP to WebSocket. From this point forward, the client and server can engage in full-duplex, real-time communication.

## Command Processing
WebSocket can be used for various types of interactions between the client and the server. Commands can be sent via WebSocket messages, and the server can parse these commands and perform corresponding actions.

### AddNode
When a client sends an `AddNode` command over the WebSocket connection, the server parses this command and takes action accordingly. This action might involve creating a new node in a data structure, or adding a new device or user to a network. The server then sends a response back to the client, such as a success message or the data of the newly created node.
In a network management system, `AddNode` could be a command to add a new node or device to the network. When the server receives this command:

1. It parses the command to extract necessary information, such as the type of the device and its IP address.
2. It adds the new device to the network topology data structure.
3. It sends a response to the client with the status of the operation.

### InstallFlow
Similarly, an InstallFlow command sent via a WebSocket connection can instruct the server to define a new network traffic flow for Quality of Service (QoS) purposes:

1. The server parses the `InstallFlow` command to extract necessary parameters, such as source and destination IP addresses, traffic type, and priority.
2. It then creates a new network flow based on these parameters.
3. The new flow is applied to the network devices using appropriate network protocols (like OpenFlow).
4. The server sends a response back to the client with the status of the operation.

In both cases, the WebSocket protocol allows for real-time, bidirectional communication, making it ideal for interactive applications and real-time data updates. It's commonly used in web applications for chat, live updates, and for real-time services in various domains including gaming, financial services, and collaborative tools.