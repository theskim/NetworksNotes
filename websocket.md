# WebSocket

WebSocket is a protocol that provides full-duplex communication between a client and a server over a single, long-lived connection. It is a part of the HTML5 specification designed to enable real-time communication in web applications, which traditionally relied on HTTP, a stateless, one-directional communication protocol. WebSocket was developed to overcome the limitations of HTTP for real-time communication.

Unlike HTTP, WebSocket provides full-duplex communication and is more efficient as, after the initial handshake, data can be sent back and forth without any additional headers, reducing the amount of network traffic.

- **Full-duplex**: Both the client and the server can send data simultaneously.
- **Persistent connection**: Unlike HTTP, the WebSocket connection stays open, allowing real-time data transfer.
- **Lower overhead**: WebSocket messages don't include extra metadata in each message after the connection is established, unlike HTTP.

## WebSocket Setup Process
1. The client requests a WebSocket connection using the WebSocket handshake protocol. This request is sent to the server in the form of a standard HTTP request with an "Upgrade: websocket" header.
2. The server responds with an HTTP response with a "101 Switching Protocols" status code. This response confirms that the server supports the WebSocket protocol and has agreed to initiate the WebSocket connection.
3. After the handshake, the connection is switched from HTTP to WebSocket, and the client and server can send and receive messages in real-time.

## AddNode
When a client sends an `AddNode` command over the WebSocket connection, the server parses this command and takes action accordingly. This action might involve creating a new node in a data structure, or adding a new device or user to a network. The server then sends a response back to the client, such as a success message or the data of the newly created node.
In a network management system, `AddNode` could be a command to add a new node or device to the network. When the server receives this command:

1. It parses the command to extract necessary information, such as the type of the device and its IP address.
2. It adds the new device to the network topology data structure.
3. It sends a response to the client with the status of the operation.

## InstallFlow
When the server receives an `InstallFlow` command, it might start a series of actions or tasks based on a defined workflow. This could involve starting a software installation process, initiating a data pipeline, or anything else depending on the specific application. The server then sends a response to the client, such as the status of the workflow or any output produced by it. `InstallFlow` could be a command to define a new network traffic flow for Quality of Service (QoS) purposes. When the server receives this command:

1. It parses the command to extract necessary information, such as source and destination IP addresses, the type of traffic, and the priority.
2. It creates a new network flow based on the provided parameters.
3. It applies the new flow to the network devices using appropriate network protocols (like OpenFlow).
4. It sends a response back to the client with the status of the operation.
