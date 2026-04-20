# Networking Study Aid

## 1. Diagrams

### OSI Model Stack
```
Application
Presentation
Session
Transport
Network
Data Link
Physical
```

### Encapsulation/Decapsulation Flow
```
Application Layer  --> Transport Layer  --> Network Layer --> Data Link Layer --> Physical Layer
Decapsulation: Physical Layer <-- Data Link Layer <-- Network Layer <-- Transport Layer <-- Application Layer
```

---

## 2. Important Differences

| Concept                  | Description                                              |
|-------------------------|----------------------------------------------------------|
| Guided vs Unguided Media| Guided media uses physical cables, unguided uses wireless signals.|  
| Baud Rate vs Bit Rate   | Baud rate is the number of signal changes per second, while bit rate is the number of bits transmitted per second.|  
| Switch vs Router        | A switch connects devices within a network, while a router connects different networks.|  
| Hub vs Switch           | A hub broadcasts to all devices, while a switch sends data to specific devices.| 
| TCP vs UDP             | TCP is connection-oriented, while UDP is connectionless.|  
| IPv4 vs IPv6           | IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses.|  
| Routing vs Forwarding   | Routing determines paths for data, while forwarding sends data along those paths.|  
| Frame vs Packet vs Segment| Frame refers to layer 2 data, packet refers to layer 3 data, and segment refers to layer 4 data.|  
| DHCP vs DNS             | DHCP assigns IP addresses dynamically, while DNS translates domain names to IP addresses.|  

---

## 3. Formulas List

- **Transmission Delay**:  \(\text{Transmission Delay} = \frac{\text{Packet Size}}{\text{Bandwidth}}\)
- **Propagation Delay**: \(\text{Propagation Delay} = \frac{\text{Distance}}{\text{Propagation Speed}}\)
- **Bit Rate/Baud Rate Relation**: For a signal with more than one bit per baud, \(\text{Bit Rate} = \text{Baud Rate} \times \log_2(n)\) where n is the number of discrete signal levels.
- **Other Core Networking Formulas**: Additional formulas per topic as needed.