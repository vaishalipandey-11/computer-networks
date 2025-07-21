# 📘 Data Link Layer – OSI Model

---

## ✅ 1. Functions of the Data Link Layer

- Framing (grouping bits into frames)
- Error detection and correction
- Flow control
- Medium Access Control (MAC)
- Addressing via MAC addresses

---

## ✅ 2. Framing (Function of Data Link Layer)

### 🔹 What is Framing?
Framing is the process of grouping a stream of bits into structured units called **frames**, so that they can be transmitted and understood correctly.

> Without framing, the receiver wouldn’t know where a message starts or ends.

### 🔹 How it Works
The Data Link Layer adds **headers and trailers** around the data:

- **Header**: Contains metadata like source/destination MAC addresses, control info.
- **Trailer**: Often includes error-checking code (like CRC).

### ➕ This helps:
- Recognize start and end of each frame.
- Provide error detection and addressing.

### 🔹 Framing Techniques

#### ✅ Byte Stuffing (Character-Oriented Protocols)
- Uses special characters (like `FLAG`) to mark frame boundaries.
- If the `FLAG` appears in data, insert an **escape** character before it.

**Example:**

  Data: Hello FLAG World
Stuffed: Hello ESC FLAG World
Frame delimiter: a unique bit pattern (e.g., 01111110)

   
#### ✅ Bit Stuffing (Bit-Oriented Protocols)
- Frame delimiter: a unique bit pattern (e.g., `01111110`)
- If sender detects **5 consecutive 1s**, it adds a 0 after them.
- Receiver removes the extra 0s during decoding.

### 🔹 Why Framing is Important

| Feature          | Why It Matters                                          |
| ---------------- | ------------------------------------------------------- |
| Clear Boundaries | Receiver knows where one frame ends, and another starts |
| Reliability      | Helps in **error checking** using trailers (like CRC)   |
| Control          | Ensures proper **flow control** and synchronization     |

---

## ✅ 3. Error Detection & Correction (Data Link Layer)

### 🔹 Error Detection
Used to detect errors introduced during transmission.

**Techniques:**
- **Parity Bit**: Adds one bit to make number of 1s even/odd.
- **Checksum**: Adds all data bytes; result is sent along. Receiver re-calculates.
- **CRC (Cyclic Redundancy Check)**:
  - Treats data as binary number & divides by fixed polynomial.
  - Remainder (CRC bits) is added.
  - Receiver re-divides to check for errors.

### ✅ Error Correction

Ensures that the receiver can **fix errors** with or without retransmission.

#### 🔹 Hamming Code
- Adds **redundant bits** to the data.
- Can detect & correct **single-bit errors**.
- Uses **position-based parity** checks.

#### 🔹 ARQ (Automatic Repeat reQuest)
- Uses **ACKs** and **timeouts**.
- If error or no ACK → resend.

**Types:**
- Stop-and-Wait ARQ
- Go-Back-N ARQ
- Selective Repeat ARQ

### ✅ Comparison: Stop-and-Wait vs Go-Back-N vs Selective Repeat

| Feature                | Stop-and-Wait ARQ       | Go-Back-N ARQ                       | Selective Repeat ARQ                |
| ---------------------- | ----------------------- | ---------------------------------- | ----------------------------------- |
| Frames Sent            | One at a time           | Multiple (within window)          | Multiple (within window)            |
| ACK                    | After each frame        | Cumulative ACK                    | Individual ACKs                     |
| On Error               | Resend that frame       | Resend that frame + all after     | Resend only the erroneous frame     |
| Efficiency             | Low                     | Medium                            | High                                |
| Receiver Buffering     | Not needed              | Minimal                           | Required (for out-of-order frames)  |
| Complexity             | Simple                  | Moderate                          | Complex                             |
| Use Case               | Simple/slow links       | Faster, minor-error networks      | High-performance, low-error links   |

---

## ✅ 4. Flow Control (Data Link Layer)

### 🔹 Purpose
Prevents sender from sending data **faster** than the receiver can process.

### 🔹 Techniques

#### ✅ Stop-and-Wait
- Sender sends one frame and **waits for ACK**.
- Simple but inefficient.

#### ✅ Sliding Window Protocol
- Sender sends **multiple frames** up to a window size.
- Receiver acknowledges received frames.
- Efficient for **high-speed networks**.

---

## ✅ 5. Access Control / MAC Protocols (Data Link Layer)

### 🔹 What is MAC?
**Medium Access Control (MAC)** decides **who** uses the shared channel and **when**.

### 🔹 Types of MAC Protocols

#### ✅ 1. ALOHA
- **Pure ALOHA**: Transmit anytime → wait if collision (~18% efficiency)
- **Slotted ALOHA**: Transmit at slot start (~37% efficiency)

#### ✅ 2. CSMA/CD (Wired Ethernet)
- **Carrier Sense**: Listen before transmit
- **Collision Detection**: Stop + backoff
- Used in **half-duplex Ethernet**

#### ✅ 3. CSMA/CA (Wi-Fi)
- Can’t detect collisions → **avoids** them
- Uses **RTS/CTS** (Request/Clear to Send)
- Suitable for **wireless networks**

### ✅ MAC Protocols Comparison

| Protocol      | Used In   | Works How?                               | Collision Handling       | Efficiency     |
| ------------- | --------- | ---------------------------------------- | ------------------------ | -------------- |
| Pure ALOHA    | Satellite | Send anytime                             | Detect after             | ~18%           |
| Slotted ALOHA | Satellite | Send at slot start                       | Detect after             | ~37%           |
| CSMA/CD       | Ethernet  | Sense → Send → Detect collision          | Retransmit after backoff | Medium-High    |
| CSMA/CA       | Wi-Fi     | Sense → Wait → Avoid collision (RTS/CTS) | Avoids before sending    | High for Wi-Fi |

---

## ✅ 6. LAN Technologies (Data Link Layer)

| Feature    | Ethernet             | Wi-Fi                   | Switch                          |
| ---------- | ------------------- | ----------------------- | ------------------------------- |
| Type       | Wired LAN           | Wireless LAN            | LAN Device                      |
| Protocol   | CSMA/CD             | CSMA/CA                 | No collision (MAC table-based)  |
| Medium     | Cables              | Radio waves             | Ethernet cables                 |
| Addressing | MAC Address         | MAC Address             | Uses MAC table                  |
| Speed      | Up to 100 Gbps      | Up to 10 Gbps (Wi-Fi 6) | Depends on connected devices    |
| Security   | Physically secure   | Needs WPA2/WPA3         | VLANs & port security           |
| OSI Layer  | Layer 2             | Layer 2                 | Layer 2 / Layer 3 (smart)       |
| Use Case   | Offices, labs       | Homes, public networks  | Core of LAN infrastructure      |

---

## ✅ 7. MAC Addressing (Media Access Control Address)

### 🔹 What is a MAC Address?
A **unique identifier** assigned to a device’s Network Interface Card (NIC).

### 🔹 Format
- 48-bit address (hexadecimal)
- Format: `00:1A:2B:3C:4D:5E`
- First 24 bits: **OUI** (manufacturer)
- Last 24 bits: **Device-specific ID**

### 🔹 Usage
- Used by Ethernet, Wi-Fi, Switches to deliver frames.
- Used **within a LAN** (Layer 2).
- **Switches** use MAC to forward frames accurately.

### 🔹 Key Points
- MAC is **hardware-based**.
- Not routable like IP.
- Used for **local delivery** only.

---

## ✅ 8. Data Link Layer Devices

| Device                          | Description                                                                                     |
| ------------------------------- | ----------------------------------------------------------------------------------------------- |
| **Switch**                      | Operates at **Layer 2**. Uses MAC addresses to forward frames. Maintains MAC address table.     |
| **Bridge**                      | Connects two LAN segments. Filters traffic based on MAC. Segments networks.                    |
| **NIC (Network Interface Card)**| Connects device to network. Has unique MAC. Responsible for frame transmission/reception.      |

---

## ✅ 9. Switching Techniques (Layer 2 Switches)

### 🔹 1. Store-and-Forward Switching
- Switch receives **entire frame**, checks CRC, then forwards.
- Reliable, but slower.

### 🔹 2. Cut-Through Switching
- Starts forwarding after reading **destination MAC**.
- Faster, but may forward **corrupted frames**.

### 🔹 Frame Communication Types

| Type      | Communication | Delivered To              | MAC Address Used                  |
| --------- | ------------- | ------------------------- | --------------------------------- |
| Unicast   | One-to-One    | Specific single device    | Unique MAC address                |
| Multicast | One-to-Group  | Selected group of devices | Multicast MAC (e.g., 01:00:5E...) |
| Broadcast | One-to-All    | All devices in the LAN    | `FF:FF:FF:FF:FF:FF`               |

---

## ✅ Dissecting an Ethernet Frame (IEEE 802.3)

An Ethernet frame is the basic unit of data at the Data Link Layer used in wired LANs.

### 🧩 Ethernet Frame Structure

| Field                        | Size (Bytes) | Description                                                                 |
| ---------------------------- | -------------| --------------------------------------------------------------------------- |
| **Preamble**                 | 7            | `10101010` pattern for **synchronization**                                  |
| **Start Frame Delimiter**    | 1            | Marks **start of frame** (`10101011`)                                       |
| **Destination MAC**          | 6            | Receiver's MAC address                                                      |
| **Source MAC**               | 6            | Sender's MAC address                                                        |
| **Type / Length**            | 2            | Protocol type (e.g., IPv4 = 0x0800) or payload size                         |
| **Payload (Data)**           | 46–1500      | Actual data (like IP packet)                                                |
| **Padding (optional)**       | varies       | Added if data < 46 bytes to meet minimum size                               |
| **CRC / FCS**                | 4            | Cyclic Redundancy Check for **error detection**                             |

> - **Minimum frame size**: 64 bytes  
> - **Maximum**: 1518 bytes  
> - If CRC error → frame is discarded

### 🧱 Ethernet Frame Layout:
[Preamble][SFD][Dest MAC][Source MAC][Type/Len][Payload][CRC]
