
### Questions 1-25: Basic Data Link Layer Concepts

**Q1.** Data Link Layer is which layer of OSI model?
a) Layer 1
b) Layer 2
c) Layer 3
d) Layer 4

**Q2.** What is the main function of Data Link Layer?
a) Routing packets
b) Converting bits to frames and error control
c) Managing sessions
d) Data encryption

**Q3.** Data Link Layer provides services to:
a) Physical Layer
b) Network Layer
c) Transport Layer
d) Session Layer

**Q4.** What is a frame?
a) Physical signal
b) Data Link Layer PDU (Protocol Data Unit)
c) Network packet
d) Application data

**Q5.** Frame synchronization is achieved by:
a) Start and end delimiters
b) Frame length field
c) Special bit patterns
d) All of the above

**Q6.** Which is NOT a Data Link Layer function?
a) Framing
b) Error control
c) Routing
d) Flow control

**Q7.** MAC stands for:
a) Media Access Control
b) Medium Access Control  
c) Multiple Access Control
d) Both a and b

**Q8.** LLC stands for:
a) Logical Link Control
b) Local Link Control
c) Limited Link Control
d) Linear Link Control

**Q9.** Data Link Layer is divided into:
a) MAC and LLC sublayers
b) Upper and Lower sublayers
c) Control and Data sublayers
d) Error and Flow sublayers

**Q10.** What is the purpose of MAC address?
a) Logical addressing
b) Physical addressing within LAN
c) Global addressing
d) Port addressing

**Q11.** MAC address length is:
a) 32 bits
b) 48 bits
c) 64 bits
d) 128 bits

**Q12.** MAC address format is:
a) Decimal notation
b) Hexadecimal notation
c) Binary notation
d) Octal notation

**Q13.** First 24 bits of MAC address represent:
a) Device ID
b) Manufacturer ID (OUI)
c) Network ID
d) Port ID

**Q14.** Broadcast MAC address is:
a) 00:00:00:00:00:00
b) FF:FF:FF:FF:FF:FF
c) 01:01:01:01:01:01
d) AA:AA:AA:AA:AA:AA

**Q15.** What is frame header used for?
a) Error detection
b) Addressing and control information
c) Data compression
d) Encryption

**Q16.** Frame trailer typically contains:
a) Source address
b) Destination address
c) Error detection code
d) Data length

**Q17.** Minimum frame size in Ethernet is:
a) 46 bytes
b) 64 bytes
c) 128 bytes
d) 1518 bytes

**Q18.** Maximum frame size in Ethernet is:
a) 64 bytes
b) 128 bytes
c) 1518 bytes
d) 9000 bytes

**Q19.** What is MTU?
a) Maximum Transmission Unit
b) Minimum Transmission Unit
c) Media Transfer Unit
d) Multiple Transfer Unit

**Q20.** Standard Ethernet MTU is:
a) 1024 bytes
b) 1500 bytes
c) 2048 bytes
d) 4096 bytes

**Q21.** Jumbo frames have MTU of:
a) 1500 bytes
b) 4500 bytes
c) 9000 bytes
d) 16000 bytes

**Q22.** Frame fragmentation is handled by:
a) Data Link Layer
b) Network Layer
c) Transport Layer
d) Application Layer

**Q23.** What is padding in Ethernet frame?
a) Extra data
b) Filler bytes to meet minimum frame size
c) Error correction bits
d) Control information

**Q24.** EtherType field indicates:
a) Frame type
b) Protocol of data in payload
c) Frame size
d) Error status

**Q25.** Data Link Layer addressing is:
a) Logical addressing
b) Physical addressing
c) Global addressing
d) Port-based addressing

### Questions 26-50: Error Detection and Correction

**Q26.** What is error detection?
a) Preventing errors
b) Identifying presence of errors
c) Correcting errors
d) Ignoring errors

**Q27.** What is error correction?
a) Detecting errors
b) Preventing errors
c) Identifying and fixing errors
d) Reporting errors

**Q28.** Parity bit can detect:
a) Single bit errors
b) Double bit errors
c) All errors
d) No errors

**Q29.** Even parity means:
a) Odd number of 1s including parity
b) Even number of 1s including parity
c) No parity bit
d) Two parity bits

**Q30.** Simple parity cannot detect:
a) Single bit error
b) Double bit error
c) Triple bit error
d) Both b and c

**Q31.** Checksum is used for:
a) Error detection only
b) Error correction only
c) Both detection and correction
d) Data compression

**Q32.** CRC stands for:
a) Cyclic Redundancy Check
b) Circular Redundancy Check
c) Cyclic Redundancy Code
d) Circular Redundancy Code

**Q33.** CRC is based on:
a) Addition
b) Subtraction
c) Polynomial division
d) Multiplication

**Q34.** CRC can detect:
a) Single bit errors
b) Burst errors
c) Multiple bit errors
d) All of the above

**Q35.** Most common CRC polynomials are:
a) CRC-8, CRC-16, CRC-32
b) CRC-4, CRC-8, CRC-12
c) CRC-1, CRC-2, CRC-4
d) CRC-64, CRC-128, CRC-256

**Q36.** Hamming code is used for:
a) Error detection only
b) Error correction only
c) Both detection and correction
d) Data encryption

**Q37.** Hamming distance is:
a) Physical distance
b) Number of bit positions in which two codewords differ
c) Time delay
d) Frequency difference

**Q38.** To detect 'd' errors, minimum Hamming distance should be:
a) d
b) d + 1
c) d - 1
d) 2d

**Q39.** To correct 't' errors, minimum Hamming distance should be:
a) t + 1
b) 2t + 1
c) t - 1
d) 2t - 1

**Q40.** Forward Error Correction (FEC):
a) Detects and corrects errors at receiver
b) Requests retransmission
c) Ignores errors
d) Only detects errors

**Q41.** Automatic Repeat Request (ARQ):
a) Corrects errors automatically
b) Requests retransmission on error detection
c) Ignores errors
d) Prevents errors

**Q42.** Which has lower overhead for few errors?
a) FEC
b) ARQ
c) Both same
d) Neither

**Q43.** Burst error affects:
a) Single bit
b) Multiple consecutive bits
c) Random bits
d) Parity bits only

**Q44.** Which is most effective for burst errors?
a) Parity check
b) Checksum
c) CRC
d) Hamming code

**Q45.** Error rate is measured as:
a) Errors per frame
b) Errors per bit (BER)
c) Errors per second
d) All of the above

**Q46.** BER stands for:
a) Bit Error Rate
b) Block Error Rate
c) Basic Error Rate
d) Burst Error Rate

**Q47.** Typical BER for fiber optic:
a) 10^-9
b) 10^-12
c) 10^-6
d) 10^-3

**Q48.** Reed-Solomon codes are used for:
a) Single bit error correction
b) Burst error correction
c) Error detection only
d) Data compression

**Q49.** Interleaving is used to:
a) Increase speed
b) Convert burst errors to random errors
c) Compress data
d) Encrypt data

**Q50.** Which error control method has highest overhead?
a) Parity
b) Checksum
c) CRC
d) Hamming code

### Questions 51-75: Flow Control and Media Access Control

**Q51.** What is flow control?
a) Controlling data flow direction
b) Managing data transmission rate between sender and receiver
c) Detecting errors
d) Routing data

**Q52.** Stop-and-Wait protocol:
a) Sends multiple frames before waiting
b) Sends one frame and waits for ACK
c) Never waits for ACK
d) Sends frames continuously

**Q53.** In Stop-and-Wait, sender waits for:
a) Timer expiry
b) Acknowledgment (ACK)
c) More data
d) Error detection

**Q54.** Efficiency of Stop-and-Wait depends on:
a) Frame size
b) Propagation delay
c) Bandwidth
d) All of the above

**Q55.** Sliding Window protocol allows:
a) Only one outstanding frame
b) Multiple outstanding frames
c) No outstanding frames
d) Fixed number of frames only

**Q56.** Window size determines:
a) Frame size
b) Number of frames that can be sent before receiving ACK
c) Buffer size
d) Network speed

**Q57.** Go-Back-N protocol:
a) Resends only erroneous frames
b) Resends all frames from error point
c) Never resends frames
d) Resends random frames

**Q58.** Selective Repeat protocol:
a) Resends only erroneous frames
b) Resends all frames from error point
c) Never resends frames
d) Resends all frames

**Q59.** Which is more efficient?
a) Go-Back-N
b) Selective Repeat
c) Stop-and-Wait
d) All same

**Q60.** Media Access Control deals with:
a) Error control
b) Shared medium access
c) Flow control
d) Routing

**Q61.** CSMA stands for:
a) Carrier Sense Multiple Access
b) Collision Sense Multiple Access
c) Control Sense Multiple Access
d) Channel Sense Multiple Access

**Q62.** CSMA/CD stands for:
a) CSMA with Collision Detection
b) CSMA with Collision Deferral
c) CSMA with Channel Detection
d) CSMA with Carrier Detection

**Q63.** CSMA/CA stands for:
a) CSMA with Collision Avoidance
b) CSMA with Carrier Avoidance
c) CSMA with Channel Access
d) CSMA with Control Access

**Q64.** Ethernet uses:
a) CSMA/CD
b) CSMA/CA
c) Token passing
d) Pure ALOHA

**Q65.** WiFi uses:
a) CSMA/CD
b) CSMA/CA
c) Token passing
d) Pure ALOHA

**Q66.** In CSMA, before transmitting:
a) Station checks if medium is idle
b) Station transmits immediately
c) Station waits for token
d) Station requests permission

**Q67.** Collision in CSMA/CD is detected by:
a) Listening while transmitting
b) Waiting for ACK
c) Timer expiry
d) Error detection

**Q68.** What happens after collision detection in CSMA/CD?
a) Continue transmission
b) Stop transmission and send jam signal
c) Wait for ACK
d) Ignore collision

**Q69.** Exponential backoff is used in:
a) Flow control
b) Error control
c) Collision resolution
d) Routing

**Q70.** Binary exponential backoff means:
a) Wait time doubles after each collision
b) Wait time halves after each collision
c) Wait time remains same
d) Wait time increases linearly

**Q71.** Token Ring uses:
a) CSMA/CD
b) Token passing
c) CSMA/CA
d) Pure ALOHA

**Q72.** In token passing, only station with _____ can transmit:
a) Data
b) Address
c) Token
d) Permission

**Q73.** Hidden terminal problem occurs in:
a) Wired networks
b) Wireless networks
c) Both
d) Neither

**Q74.** RTS/CTS is used to solve:
a) Error problems
b) Flow control problems
c) Hidden terminal problem
d) Routing problems

**Q75.** Pure ALOHA efficiency is approximately:
a) 18%
b) 37%
c) 50%
d) 100%

### Questions 76-100: Network Devices and Protocols

**Q76.** Which device operates at Data Link Layer?
a) Hub
b) Switch
c) Router
d) Gateway

**Q77.** Bridge operates at:
a) Physical Layer
b) Data Link Layer
c) Network Layer
d) Transport Layer

**Q78.** Switch is a:
a) Single port bridge
b) Two port bridge
c) Multi-port bridge
d) Wireless bridge

**Q79.** MAC address table is maintained by:
a) Hub
b) Switch
c) Router
d) Repeater

**Q80.** Learning bridge:
a) Learns MAC addresses from source addresses
b) Learns IP addresses
c) Learns port numbers
d) Never learns anything

**Q81.** Flooding in switch means:
a) Too much data
b) Broadcasting frame to all ports except source
c) Discarding frames
d) Learning addresses

**Q82.** Spanning Tree Protocol (STP) prevents:
a) Errors
b) Loops in bridged networks
c) Collisions
d) Flow control problems

**Q83.** VLAN stands for:
a) Virtual Local Area Network
b) Variable Local Area Network
c) Verified Local Area Network
d) Visual Local Area Network

**Q84.** VLANs are created by:
a) Hubs
b) Switches
c) Repeaters
d) Cables

**Q85.** Trunk port carries:
a) Single VLAN traffic
b) Multiple VLAN traffic
c) No traffic
d) Control traffic only

**Q86.** 802.1Q is used for:
a) Error control
b) VLAN tagging
c) Flow control
d) Media access control

**Q87.** Collision domain of a switch:
a) All ports together
b) Each port separate
c) Two ports together
d) No collision domain

**Q88.** Broadcast domain of a switch:
a) Each port separate
b) All ports together
c) Two ports together
d) No broadcast domain

**Q89.** Half-duplex switch port can:
a) Send and receive simultaneously
b) Send or receive at a time
c) Only send
d) Only receive

**Q90.** Full-duplex switch port can:
a) Send and receive simultaneously
b) Send or receive at a time
c) Only send
d) Only receive

**Q91.** Auto-negotiation determines:
a) Speed only
b) Duplex only
c) Both speed and duplex
d) Neither speed nor duplex

**Q92.** Store-and-forward switching:
a) Forwards immediately after receiving destination address
b) Stores complete frame before forwarding
c) Never forwards frames
d) Forwards random frames

**Q93.** Cut-through switching:
a) Forwards immediately after receiving destination address
b) Stores complete frame before forwarding
c) Never forwards frames
d) Discards all frames

**Q94.** Which switching method has lowest latency?
a) Store-and-forward
b) Cut-through
c) Fragment-free
d) All same

**Q95.** ARP stands for:
a) Address Resolution Protocol
b) Automatic Resolution Protocol
c) Advanced Resolution Protocol
d) Applied Resolution Protocol

**Q96.** ARP maps:
a) MAC to IP address
b) IP to MAC address
c) IP to port number
d) MAC to port number

**Q97.** RARP stands for:
a) Reverse Address Resolution Protocol
b) Random Address Resolution Protocol
c) Remote Address Resolution Protocol
d) Rapid Address Resolution Protocol

**Q98.** Ethernet frame format is defined by:
a) IEEE 802.1
b) IEEE 802.3
c) IEEE 802.11
d) IEEE 802.5

**Q99.** Token Ring is defined by:
a) IEEE 802.1
b) IEEE 802.3
c) IEEE 802.5
d) IEEE 802.11

**Q100.** WiFi is defined by:
a) IEEE 802.3
b) IEEE 802.5
c) IEEE 802.11
d) IEEE 802.15

---

## Answer Key

| Q | Ans | Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|-----|---|-----|---|-----|---|-----|---|-----|
| 1 | b | 21 | c | 41 | b | 61 | a | 81 | b |
| 2 | b | 22 | b | 42 | b | 62 | a | 82 | b |
| 3 | b | 23 | b | 43 | b | 63 | a | 83 | a |
| 4 | b | 24 | b | 44 | c | 64 | a | 84 | b |
| 5 | d | 25 | b | 45 | d | 65 | b | 85 | b |
| 6 | c | 26 | b | 46 | a | 66 | a | 86 | b |
| 7 | d | 27 | c | 47 | b | 67 | a | 87 | b |
| 8 | a | 28 | a | 48 | b | 68 | b | 88 | b |
| 9 | a | 29 | b | 49 | b | 69 | c | 89 | b |
| 10| b | 30 | d | 50 | d | 70 | a | 90 | a |
| 11| b | 31 | a | 51 | b | 71 | b | 91 | c |
| 12| b | 32 | a | 52 | b | 72 | c | 92 | b |
| 13| b | 33 | c | 53 | b | 73 | b | 93 | a |
| 14| b | 34 | d | 54 | d | 74 | c | 94 | b |
| 15| b | 35 | a | 55 | b | 75 | a | 95 | a |
| 16| c | 36 | c | 56 | b | 76 | b | 96 | b |
| 17| b | 37 | b | 57 | b | 77 | b | 97 | a |
| 18| c | 38 | b | 58 | a | 78 | c | 98 | b |
| 19| a | 39 | b | 59 | b | 79 | b | 99 | c |
| 20| b | 40 | a | 60 | b | 80 | a | 100| c |

## Quick Study Points for Placement:
- **Data Link Layer = Layer 2 of OSI**
- **Main functions**: Framing, Error control, Flow control, MAC
- **Key concepts**: MAC address (48-bit), Ethernet frame, Switch operation
- **Error control**: Parity, CRC, Hamming code, ARQ vs FEC
- **Flow control**: Stop-and-Wait, Sliding Window, Go-Back-N
- **MAC protocols**: CSMA/CD (Ethernet), CSMA/CA (WiFi), Token passing
- **Devices**: Bridge/Switch (Layer 2), Hub (Layer 1), Router (Layer 3)
- **Important standards**: 802.3 (Ethernet), 802.11 (WiFi), 802.5 (Token Ring)
