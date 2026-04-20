# Chapter 4: Data Link Layer

## 1. What is the Data Link Layer?

The Data Link Layer is the second layer of the OSI model. It provides node-to-node delivery of data over a single link.

### Main idea
The physical layer sends raw bits, but those bits alone are not enough to ensure proper communication between directly connected devices. The data link layer organizes those bits into frames, adds addresses, and handles error detection.

### In simple words
This layer makes sure that data can move safely from one directly connected device to another.

### GATE point
The data link layer works with frames and MAC addresses.

---

## 2. Why do we need the Data Link Layer?

When data is sent over a network, raw bits may get corrupted or misinterpreted. The data link layer solves this by providing:

- framing
- error detection
- flow control
- medium access control
- local delivery between neighboring nodes

### Why it is important
Without this layer, devices connected on the same link would not know:
- where a message starts and ends
- who the message is for
- whether the message got damaged during transmission

---

## 3. Responsibilities of the Data Link Layer

The main responsibilities are:

1. Framing
2. Physical addressing
3. Error detection
4. Flow control
5. Medium access control
6. Reliable node-to-node communication

---

## 4. Framing

### What is framing?
Framing is the process of dividing the bit stream into manageable units called frames.

### Why framing is needed
The receiver must know:
- where a frame starts
- where it ends
- what data belongs together

### Example
If a large message is sent as a continuous bit stream, framing allows the receiver to separate it into meaningful units.

### Frame structure
A frame usually contains:
- header
- payload
- trailer

### GATE point
Framing is one of the most basic functions of the data link layer.

---

## 5. Addressing in the Data Link Layer

The data link layer uses physical addressing, also called MAC addressing.

### MAC address
A MAC address is a hardware address assigned to a network interface card.

### Characteristics of MAC address
- usually 48 bits long
- written in hexadecimal form
- globally unique in most cases
- used for local delivery within a LAN

### Example
A MAC address may look like:
00:1A:2B:3C:4D:5E

### Important
- IP address works at the network layer
- MAC address works at the data link layer

### GATE point
Do not confuse IP address with MAC address.

---

## 6. Error Detection

Transmission may introduce errors. The data link layer detects these errors.

### Why error detection is required
Signals can get corrupted because of:
- noise
- attenuation
- interference
- faulty hardware

### Common error detection methods
- parity check
- checksum
- cyclic redundancy check (CRC)

---

### 6.1 Parity check
A parity bit is added to make the number of 1s either even or odd.

#### Types
- even parity
- odd parity

#### Limitation
It can detect only some errors, not all.

---

### 6.2 Checksum
A checksum is computed from the data and sent along with it. The receiver recomputes and compares.

#### Use
It is widely used in protocols to detect errors.

---

### 6.3 Cyclic Redundancy Check (CRC)
CRC is a strong and widely used error detection method.

#### Working idea
The sender treats the frame as a polynomial and divides it by a generator polynomial. The remainder is appended to the data.

#### Advantage
CRC can detect many kinds of errors very effectively.

#### GATE point
CRC is one of the most important error detection techniques in GATE.

---

## 7. Error Detection vs Error Correction

### Error detection
Finds whether an error occurred.

### Error correction
Finds and fixes the error.

### In data link layer
The main focus is often on detection, but some protocols may also support correction.

### GATE point
Error detection and error correction are not the same.

---

## 8. Flow Control

### What is flow control?
Flow control ensures that a fast sender does not overwhelm a slow receiver.

### Why it is needed
If the sender transmits too quickly, the receiver’s buffer may overflow and data can be lost.

### Goal
Match the sender’s rate with the receiver’s capacity.

### Methods
- stop-and-wait
- sliding window

---

### 8.1 Stop-and-Wait
The sender sends one frame and waits for acknowledgment before sending the next.

#### Advantage
Simple

#### Disadvantage
Low efficiency for long-distance links

---

### 8.2 Sliding Window
The sender can send multiple frames before needing acknowledgment.

#### Advantage
Better utilization and efficiency

#### GATE point
Sliding window is more efficient than stop-and-wait.

---

## 9. Medium Access Control (MAC)

### What is MAC?
MAC controls how multiple devices share the same communication medium.

### Why it is needed
If many devices share a channel, they may try to transmit at the same time, causing collisions.

### MAC functions
- decide who can transmit
- avoid or handle collisions
- coordinate access to the medium

### MAC protocols
- ALOHA
- Slotted ALOHA
- CSMA
- CSMA/CD
- CSMA/CA

---

### 9.1 ALOHA
A simple random-access protocol.

#### Pure ALOHA
A station can transmit whenever it wants.

#### Slotted ALOHA
Time is divided into slots, and transmission starts only at slot boundaries.

#### GATE point
Slotted ALOHA is more efficient than Pure ALOHA.

---

### 9.2 CSMA
Carrier Sense Multiple Access.

#### Idea
A device listens to the medium before transmitting.

#### If medium is idle
Transmit

#### If medium is busy
Wait

---

### 9.3 CSMA/CD
Carrier Sense Multiple Access with Collision Detection.

#### Used in
Traditional Ethernet

#### Working
- sense the medium
- transmit if idle
- detect collision during transmission
- stop and retry if collision occurs

#### GATE point
CSMA/CD is associated with wired Ethernet.

---

### 9.4 CSMA/CA
Carrier Sense Multiple Access with Collision Avoidance.

#### Used in
Wireless networks such as Wi-Fi

#### Why avoidance is needed
Collision detection is hard in wireless due to hidden node and signal limitations.

#### GATE point
CSMA/CA is used in wireless LANs.

---

## 10. LLC and MAC Sublayers

The data link layer is divided into two sublayers:

1. LLC — Logical Link Control
2. MAC — Media Access Control

### 10.1 LLC sublayer
LLC provides:
- error and flow control services
- interface to the network layer

### 10.2 MAC sublayer
MAC provides:
- access control to shared media
- physical addressing
- collision handling

### GATE point
MAC is more closely associated with how devices access the channel.

---

## 11. Frames

### What is a frame?
A frame is the data unit of the data link layer.

### Frame components
- header
- payload
- trailer

### Why frames are useful
Frames help organize transmitted bits and add control information for reliable local delivery.

### GATE point
Transport layer data unit = segment
Network layer data unit = packet
Data link layer data unit = frame
Physical layer data unit = bits

---

## 12. Types of Data Link Errors

### 12.1 Single-bit error
Only one bit is corrupted.

### 12.2 Burst error
A group of bits is corrupted.

### GATE point
CRC is especially useful for detecting burst errors.

---

## 13. Link Layer Devices and Concepts

### Switch
A switch works mainly at the data link layer.

#### It uses
- MAC addresses
- frame forwarding

### Bridge
A bridge connects two LAN segments and filters frames based on MAC addresses.

### Repeater
A repeater is a physical layer device, not data link layer.

### Hub
A hub works at the physical layer and broadcasts data to all ports.

### GATE point
Switch and bridge operate at a higher level than hub.

---

## 14. Ethernet and Data Link Layer

Ethernet is a very important technology based on the data link layer.

### Why it matters
Most wired LANs use Ethernet concepts.

### Ethernet functions
- frame format
- MAC addressing
- collision handling in older networks
- switching in modern networks

### Important
Modern Ethernet is usually switched, not hub-based.

---

## 15. Common GATE Comparisons

### Data link layer vs network layer
| Feature | Data Link Layer | Network Layer |
|---|---|---|
| Delivery | Node to node | Source to destination |
| Address | MAC address | IP address |
| Data unit | Frame | Packet |
| Main function | Framing, MAC, error detection | Routing, logical addressing |

### Switch vs Router
| Feature | Switch | Router |
|---|---|---|
| Layer | Data link | Network |
| Address used | MAC | IP |
| Forwarding unit | Frame | Packet |

### Hub vs Switch
| Feature | Hub | Switch |
|---|---|---|
| Layer | Physical | Data link |
| Forwarding | To all ports | To selected port |
| Intelligence | None | Uses MAC table |

---

## 16. Important GATE Questions from This Chapter

You should be able to answer:
- What is framing?
- What is the purpose of MAC addressing?
- What is the difference between error detection and correction?
- What is CRC used for?
- Why is CSMA/CD used in Ethernet?
- Why is CSMA/CA used in wireless networks?
- What is the difference between a bridge and a switch?
- What does the LLC sublayer do?
- What does the MAC sublayer do?

---

## 17. PYQ Focus Areas

The following topics are frequently useful in GATE:
- frame structure
- error detection techniques
- CRC
- parity
- checksum
- CSMA/CD
- CSMA/CA
- ALOHA and slotted ALOHA
- MAC vs IP
- switch vs router
- LLC vs MAC

---

## 18. Quick Revision Summary

- The data link layer provides node-to-node delivery.
- It works with frames and MAC addresses.
- It handles framing, error detection, flow control, and medium access.
- CRC is a strong error detection method.
- CSMA/CD is for wired Ethernet.
- CSMA/CA is for wireless networks.
- Switches work at the data link layer.

---

## 19. Trusted References
- Cisco Networking Academy: https://www.netacad.com/
- NPTEL Computer Networks: https://nptel.ac.in/
- IETF RFCs: https://www.rfc-editor.org/
- Tanenbaum, Computer Networks
- Kurose & Ross, Computer Networking: A Top-Down Approach

---

## 20. Final GATE Tip

Do not memorize the data link layer as only “frame layer.”
Understand:
- how frames are formed
- how errors are detected
- how multiple devices share a medium
- how switches and bridges differ
- why MAC addressing is needed
