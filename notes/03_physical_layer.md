# Physical Layer

The Physical Layer is the first layer in the OSI model and is responsible for the transmission and reception of unstructured raw data between a sender and a receiver. This layer deals with the physical connection between devices and transmits data over various transmission media.

## 1. What the Physical Layer Actually Does

The physical layer is responsible for turning bits into signals and sending those signals across the communication medium.

It does not understand meaning, addresses, frames, or packets. Its only job is to carry raw bits from one end to the other.

### In simple words
- Upper layers create data
- The physical layer converts those bits into signals
- Those signals travel through cable, fiber, or wireless medium
- The receiver converts the signal back into bits

### Main responsibilities
- bit transmission
- signal representation
- bit synchronization
- line configuration
- physical topology definition
- connector and cable characteristics
- data rate support

### GATE point
The physical layer works with **bits and signals**, not frames or packets.

---

## 2. Signals

A signal is a physical representation of data.

### 2.1 Analog signals
Analog signals are continuous signals that vary smoothly over time.

#### Examples
- sound waves
- radio signals
- temperature variation

#### Properties
- continuous in time and amplitude
- can take infinitely many values in a range

### 2.2 Digital signals
Digital signals are discrete signals that represent data using distinct levels.

#### Example
- binary 0 and 1

#### Properties
- sudden changes between levels
- easier to store and process in computers

### 2.3 Analog vs digital in networking
In real networks, data may be digital, but it is often transmitted over physical media as electrical, optical, or radio signals.

### GATE point
Do not confuse **data** with **signal**. Data is the information; signal is the physical form used to carry that information.

---

## 3. Transmission Media

Transmission media is the path used to send signals.

There are two major categories:
- guided media
- unguided media

### 3.1 Guided media
Guided media uses a physical path such as cable.

#### Types
- twisted pair cable
- coaxial cable
- optical fiber

#### Key features
- more secure than wireless
- less affected by interference than wireless in many cases
- suitable for wired LANs and long-distance backbones

### 3.2 Unguided media
Unguided media uses free space as the transmission path.

#### Types
- radio waves
- microwaves
- infrared
- satellite communication

#### Key features
- no physical cable required
- supports mobility
- more vulnerable to interference and noise

### Guided vs unguided comparison
| Feature | Guided | Unguided |
|---|---|---|
| Medium | Physical cable | Air / free space |
| Mobility | Low | High |
| Interference | Lower | Higher |
| Security | Better | Lower |
| Cost of deployment | Depends on cabling | Often lower for mobility |

---

## 4. Guided Media in Detail

### 4.1 Twisted pair cable
Two insulated copper wires twisted together.

#### Why twisting is used
Twisting reduces electromagnetic interference and crosstalk.

#### Types
- Unshielded Twisted Pair (UTP)
- Shielded Twisted Pair (STP)

#### Uses
- telephone lines
- Ethernet LANs

#### Advantages
- cheap
- easy to install
- widely available

#### Disadvantages
- more attenuation than fiber
- lower bandwidth than fiber
- more noise than coax or fiber

---

### 4.2 Coaxial cable
A coaxial cable has a central conductor surrounded by insulation, shielding, and an outer conductor.

#### Structure
- inner conductor
- dielectric insulator
- metallic shield
- protective outer jacket

#### Uses
- cable television
- broadband internet in some setups
- older Ethernet systems

#### Advantages
- better shielding than twisted pair
- supports higher frequency than twisted pair

#### Disadvantages
- bulkier and less flexible than twisted pair
- more expensive than twisted pair

---

### 4.3 Optical fiber
Optical fiber uses light to carry data.

#### Structure
- core
- cladding
- protective coating

#### Working idea
Light is guided through the core by total internal reflection.

#### Types
- Single-mode fiber
- Multi-mode fiber

#### Advantages
- very high bandwidth
- very low attenuation
- immune to electromagnetic interference
- secure and light-weight

#### Disadvantages
- installation is expensive
- fragile compared to copper
- splicing and maintenance need special tools

#### GATE point
Fiber is preferred for high-speed backbone communication because of its bandwidth and low attenuation.

---

## 5. Unguided Media in Detail

### 5.1 Radio waves
Radio waves are widely used for wireless communication.

#### Uses
- broadcasting
- Wi-Fi
- mobile communication
- Bluetooth

#### Features
- can travel long distances
- can pass through walls in many cases
- prone to interference

---

### 5.2 Microwaves
Microwaves are used in point-to-point communication and satellite links.

#### Uses
- cellular backhaul
- satellite communication
- radar
- wireless links between towers

#### Features
- directional
- line-of-sight communication often needed
- affected by obstacles and weather

---

### 5.3 Infrared
Infrared is used for short-range communication.

#### Uses
- remote controls
- short-distance device communication

#### Features
- short range
- cannot pass through walls easily
- low interference in enclosed spaces

---

### 5.4 Satellite communication
A satellite acts as a relay station in space.

#### Uses
- TV broadcasting
- navigation
- long-distance data communication

#### Features
- very large coverage area
- high delay compared to terrestrial links
- useful where cable is difficult to deploy

---

## 6. Bandwidth, Bit Rate, and Baud Rate

These terms are very important in GATE.

### 6.1 Bandwidth
Bandwidth is the range of frequencies a channel can carry.

#### In practical networking
It is often used to mean the maximum data-carrying capacity of a channel.

### 6.2 Bit rate
Bit rate is the number of bits transmitted per second.

#### Unit
bps, Kbps, Mbps, Gbps

### 6.3 Baud rate
Baud rate is the number of signal symbols transmitted per second.

#### Important relation
If one symbol carries multiple bits, bit rate can be greater than baud rate.

### Relation
Bit Rate = Baud Rate × Number of bits per symbol

### Example
If each symbol carries 2 bits and baud rate is 1000 baud, then bit rate is 2000 bps.

### GATE trap
Bandwidth and bit rate are not the same thing.

---

## 7. Transmission Performance and Formulas

### 7.1 Transmission delay
Transmission delay is the time needed to place all bits of a packet on the link.

#### Formula
Transmission delay = Packet size / Bandwidth

### 7.2 Propagation delay
Propagation delay is the time needed for a signal to travel from sender to receiver.

#### Formula
Propagation delay = Distance / Propagation speed

### 7.3 Bandwidth-delay idea
A channel can have very high bandwidth but still high delay if the distance is large.

### GATE point
Transmission delay depends on packet size and link rate.
Propagation delay depends on distance and signal speed.

---

## 8. Transmission Impairments

When data travels through a medium, it may get degraded.

### 8.1 Attenuation
Attenuation is the loss of signal strength over distance.

#### Why it happens
- resistance in cables
- scattering in fiber
- absorption in media

#### Solution
Amplifiers and repeaters are used to restore the signal.

### 8.2 Distortion
Distortion occurs when different parts of a signal travel differently and the signal shape changes.

#### Effect
The received signal is not the same as the transmitted signal.

### 8.3 Noise
Noise is unwanted energy that interferes with the signal.

#### Common types
- thermal noise
- crosstalk
- impulse noise
- intermodulation noise

### 8.4 Crosstalk
Crosstalk is unwanted coupling between nearby communication paths.

### GATE point
Attenuation, distortion, and noise are the main causes of signal impairment.

---

## 9. Line Coding

Line coding is the process of converting digital data into digital signals.

### Why line coding is needed
Digital data cannot be sent directly in abstract form. It must be represented by electrical or optical signal patterns.

### 9.1 NRZ
NRZ stands for Non-Return-to-Zero.

#### Idea
The signal does not return to zero between bits.

#### Limitation
Long runs of 0s or 1s may cause synchronization problems.

### 9.2 Manchester encoding
In Manchester encoding, each bit has a transition in the middle.

#### Advantage
Good synchronization.

#### Disadvantage
Requires more bandwidth than NRZ.

### GATE point
Manchester encoding is self-clocking.

---

## 10. Multiplexing

Multiplexing is the technique of combining multiple signals to share a single communication channel.

### Why multiplexing is used
- saves bandwidth resources
- improves channel utilization
- reduces cost

### 10.1 Frequency Division Multiplexing (FDM)
The channel is divided into different frequency bands.

#### Used in
- radio broadcasting
- cable systems

### 10.2 Time Division Multiplexing (TDM)
Different users share the channel in different time slots.

#### Used in
- digital telephony
- some communication links

### 10.3 Wavelength Division Multiplexing (WDM)
Used in optical fiber systems, where different wavelengths of light carry different data streams.

### 10.4 Code Division Multiplexing (CDM)
Different users share the same frequency band but use different codes.

### GATE point
Know the difference between FDM, TDM, WDM, and CDM.

---

## 11. Switching Techniques

Switching is the process of moving data from source to destination through intermediate nodes.

### 11.1 Circuit switching
A dedicated path is established before communication begins.

#### Example
Traditional telephone networks.

#### Pros
- guaranteed path
- predictable delay

#### Cons
- waste of resources when idle

### 11.2 Packet switching
Data is broken into packets and each packet is routed independently.

#### Example
Internet communication.

#### Pros
- efficient use of resources
- flexible

#### Cons
- variable delay
- packets may take different paths

### 11.3 Message switching
The entire message is stored and forwarded at each intermediate node.

#### Cons
- large storage requirement
- high delay

### GATE point
Packet switching is the basis of the Internet.

---

## 12. Physical Layer Devices

### Repeater
- regenerates weak signals
- used to extend communication distance

### Hub
- broadcasts incoming signal to all ports
- works at physical layer
- now largely obsolete

### Modem
- modulates and demodulates signals
- used to convert digital data into transmission-friendly form and back

### Transceiver
- can transmit and receive signals

### GATE point
A hub operates at the physical layer, while a switch is mainly associated with the data link layer.

---

## 13. Important Comparison Tables

### 13.1 Transmission media comparison
| Media | Speed | Cost | Noise resistance | Range |
|---|---|---|---|---|
| Twisted pair | Moderate | Low | Low to moderate | Short |
| Coaxial | Better than twisted pair | Moderate | Better | Medium |
| Fiber optic | Very high | Higher | Very high | Long |

### 13.2 Communication media comparison
| Type | Example | Mobility |
|---|---|---|
| Guided | Cable, fiber | Low |
| Unguided | Radio, microwave | High |

### 13.3 Switching comparison
| Switching | Path | Delay | Resource usage |
|---|---|---|---|
| Circuit | Dedicated | Predictable | Less efficient when idle |
| Packet | Shared | Variable | Efficient |
| Message | Store and forward whole message | High | Inefficient |

---

## 14. GATE Important Points

You should remember:
- physical layer handles bits and signals
- transmission media can be guided or unguided
- fiber has high bandwidth and low attenuation
- baud rate is symbols per second
- bit rate is bits per second
- transmission delay and propagation delay are different
- attenuation, distortion, and noise are impairments
- FDM, TDM, WDM, and CDM are multiplexing methods
- circuit switching and packet switching are different
- hub works at physical layer

---

## 15. PYQ-style Questions

### Concept-based
- Which medium has the least attenuation?
- Which switching technique is used by the Internet?
- What is the relationship between baud rate and bit rate?
- Which device works at the physical layer?
- Why is optical fiber preferred for backbone networks?

### Formula-based
- Calculate transmission delay
- Calculate propagation delay
- Compare bit rate and baud rate

### Comparison-based
- Twisted pair vs coaxial vs fiber
- Circuit switching vs packet switching
- Guided vs unguided media

---

## 16. Quick Revision Summary

- Physical layer sends raw bits as signals.
- It deals with media, signaling, and transmission characteristics.
- Guided media uses cable; unguided media uses free space.
- Fiber optics provide high speed and low attenuation.
- Bit rate and baud rate are different.
- Attenuation, distortion, and noise degrade signals.
- Multiplexing improves channel utilization.
- Packet switching is used in the Internet.

---

## 17. Trusted References
- Cisco Networking Academy: https://www.netacad.com/
- NPTEL Computer Networks: https://nptel.ac.in/
- IETF RFCs: https://www.rfc-editor.org/
- IEEE Communications Society: https://www.comsoc.org/
- Tanenbaum, Computer Networks
- Kurose & Ross, Computer Networking: A Top-Down Approach

---

## 18. Final GATE Tip

Do not treat the physical layer as only cable and wireless.
Understand the formulas, impairments, media types, multiplexing, switching, and devices because GATE questions often combine concepts from multiple parts of this chapter.