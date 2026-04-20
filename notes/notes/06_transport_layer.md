# Chapter 6: Transport Layer

## 1. What is the Transport Layer?

The Transport Layer is the fourth layer of the OSI model. It provides end-to-end communication between processes running on different hosts.

### Main idea
The network layer gets a packet from one host to another, but the transport layer ensures that the right application process receives the data.

### In simple words
This layer is responsible for delivering data to the correct program on the destination machine.

### GATE point
The transport layer works with segments and ports.

---

## 2. Why do we need the Transport Layer?

A single computer may run many applications at the same time:
- browser
- email client
- file transfer
- chat app
- video call application

The transport layer makes sure data goes to the correct application.

### Why it is important
Without the transport layer, the destination host would receive data but would not know which application should use it.

---

## 3. Main Responsibilities of the Transport Layer

The transport layer is responsible for:

1. Process-to-process delivery
2. Segmentation and reassembly
3. Port addressing
4. Flow control
5. Error control
6. Multiplexing and demultiplexing
7. Connection management

---

## 4. Process-to-Process Delivery

### What is process-to-process delivery?
It means delivery of data from one application process on the source machine to another application process on the destination machine.

### How it is achieved
This is done using port numbers.

### Example
- HTTP uses port 80
- HTTPS uses port 443
- FTP uses ports 20 and 21

### GATE point
Network layer delivers host-to-host; transport layer delivers process-to-process.

---

## 5. Port Addressing

### What is a port?
A port is a logical endpoint used to identify a specific application on a host.

### Why ports are needed
An IP address identifies the machine, but a port identifies the application running on that machine.

### Example
If a browser and email client are open on the same computer, port numbers help the system send the data to the correct app.

### Well-known ports
- 20, 21: FTP
- 22: SSH
- 23: Telnet
- 25: SMTP
- 53: DNS
- 80: HTTP
- 443: HTTPS

### GATE point
Port number belongs to the transport layer.

---

## 6. Segmentation and Reassembly

### Segmentation
The transport layer divides large messages into smaller pieces called segments.

### Reassembly
At the destination, these segments are combined back into the original message.

### Why it is needed
- networks may have size limits
- segmentation improves transmission efficiency
- helps in error recovery

### GATE point
Transport layer data unit = segment.

---

## 7. Multiplexing and Demultiplexing

### Multiplexing
Multiple application streams from the source are combined for transmission.

### Demultiplexing
At the destination, the transport layer separates data and delivers it to the correct process.

### How it works
Port numbers are used to identify the correct process.

### GATE point
Demultiplexing is a major transport layer function.

---

## 8. Flow Control

### What is flow control?
Flow control ensures that a sender does not overwhelm a receiver.

### Why it is needed
If the sender sends too quickly, the receiver buffer may overflow.

### Transport layer role
The transport layer can regulate the rate of data transmission between endpoints.

### Example
TCP uses flow control with a sliding window.

---

## 9. Error Control

### What is error control?
Error control ensures reliable communication by detecting and recovering from lost, corrupted, or duplicate segments.

### What error control may include
- sequence numbers
- acknowledgments
- retransmissions
- timers

### GATE point
Reliable transport protocols use acknowledgments and retransmission.

---

## 10. Connection-Oriented and Connectionless Service

### 10.1 Connection-oriented service
A connection is established before data transfer.

#### Example
TCP

#### Features
- reliable
- ordered delivery
- connection setup required
- more overhead

---

### 10.2 Connectionless service
Data is sent without establishing a prior connection.

#### Example
UDP

#### Features
- no connection setup
- low overhead
- faster
- no delivery guarantee

### GATE point
TCP is connection-oriented; UDP is connectionless.

---

## 11. TCP (Transmission Control Protocol)

TCP is a connection-oriented, reliable transport protocol.

### TCP features
- reliable delivery
- ordered delivery
- flow control
- congestion control
- error detection
- connection management

### TCP uses
- web browsing
- email
- file transfer
- remote login

### Why TCP is reliable
TCP uses:
- sequence numbers
- acknowledgments
- retransmissions
- timers
- checksum

### GATE point
TCP is the most important transport protocol for reliable communication.

---

## 12. TCP Connection Management

### 12.1 Establishing connection
TCP uses a three-way handshake.

#### Steps
1. Client sends SYN
2. Server replies SYN-ACK
3. Client sends ACK

### Why handshake is needed
It synchronizes sequence numbers and establishes a connection.

---

### 12.2 Terminating connection
TCP connection termination uses a four-step closing process in typical cases.

### GATE point
Three-way handshake is a very common exam question.

---

## 13. TCP Reliability Features

### Sequence numbers
Used to keep track of bytes or segments and maintain order.

### Acknowledgments
Used to confirm successful receipt.

### Retransmission
If acknowledgment is not received, TCP resends data.

### Checksum
Detects corruption in the TCP segment.

### Sliding window
Improves efficiency while maintaining reliability.

### GATE point
TCP reliability depends on sequence numbers, ACKs, retransmission, and flow control.

---

## 14. UDP (User Datagram Protocol)

UDP is a connectionless transport protocol.

### UDP features
- no connection setup
- low overhead
- faster than TCP
- no guaranteed delivery
- no ordering guarantee

### UDP uses
- streaming
- VoIP
- DNS
- online gaming
- live media

### Why UDP is used
When speed matters more than reliability, UDP is preferred.

### GATE point
UDP is simple and lightweight compared to TCP.

---

## 15. TCP vs UDP

| Feature | TCP | UDP |
|---|---|---|
| Connection | Connection-oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Ordering | Ordered delivery | No ordering guarantee |
| Speed | Slower | Faster |
| Overhead | Higher | Lower |
| Use cases | Web, email, file transfer | Streaming, DNS, gaming |

### GATE point
This comparison is very frequently tested.

---

## 16. Segment / Packet / Datagram

### At transport layer
The data unit is called a segment.

### At network layer
The data unit is called a packet or datagram.

### At data link layer
The data unit is called a frame.

### At physical layer
The data unit is bits.

### GATE point
Know the data unit name for each layer.

---

## 17. Sockets

### What is a socket?
A socket is an endpoint for communication between two processes.

### Socket components
- IP address
- port number

### Why it is important
Sockets are used by applications to communicate over a network.

### Example
A web server socket can be represented by IP + port 80 or 443.

### GATE point
Socket = IP address + port number.

---

## 18. Quality of Service (QoS) Concepts

Transport protocols may be affected by:
- delay
- jitter
- throughput
- reliability

### Delay
Time taken for data to travel.

### Jitter
Variation in delay.

### Throughput
Amount of data successfully delivered per unit time.

### GATE point
For real-time applications, jitter and delay are important.

---

## 19. Transport Layer Devices and Concepts

The transport layer is mostly implemented in software inside the operating system.

### It works with
- sockets
- ports
- process identifiers
- buffering

### Notable point
Routers do not generally perform transport-layer processing for normal forwarding.

---

## 20. Common GATE Comparisons

### Transport layer vs network layer
| Feature | Transport Layer | Network Layer |
|---|---|---|
| Delivery | Process to process | Host to host |
| Addressing | Port number | IP address |
| Data unit | Segment | Packet |
| Main function | End-to-end communication | Routing and forwarding |

### TCP vs UDP
| Feature | TCP | UDP |
|---|---|---|
| Connection | Yes | No |
| Reliability | Yes | No |
| Ordering | Yes | No |
| Speed | Lower | Higher |

### Socket vs port
| Feature | Socket | Port |
|---|---|---|
| Definition | Endpoint of communication | Logical application identifier |
| Contains | IP + port | Number only |

---

## 21. Important GATE Questions from This Chapter

You should be able to answer:
- What is process-to-process delivery?
- What is the role of port numbers?
- What is the difference between segmentation and reassembly?
- What is the difference between TCP and UDP?
- What is the three-way handshake?
- Why is TCP reliable?
- What is the use of a socket?
- What is multiplexing and demultiplexing?
- What is flow control?
- What is error control?

---

## 22. PYQ Focus Areas

These topics are especially important:
- TCP vs UDP
- three-way handshake
- sequence numbers
- acknowledgments
- retransmission
- flow control
- sockets
- port numbers
- process-to-process communication
- segment data unit

---

## 23. Quick Revision Summary

- The transport layer provides process-to-process communication.
- It works with segments and ports.
- TCP is reliable and connection-oriented.
- UDP is fast and connectionless.
- TCP uses handshake, ACKs, retransmission, and flow control.
- Ports identify applications.
- Sockets are IP + port.

---

## 24. Trusted References
- Cisco Networking Academy: https://www.netacad.com/
- NPTEL Computer Networks: https://nptel.ac.in/
- IETF RFCs: https://www.rfc-editor.org/
- Tanenbaum, Computer Networks
- Kurose & Ross, Computer Networking: A Top-Down Approach

---

## 25. Final GATE Tip

For the transport layer, focus on:
- TCP vs UDP
- ports and sockets
- segmentation and reassembly
- flow control
- error control
- three-way handshake
- process-to-process communication
