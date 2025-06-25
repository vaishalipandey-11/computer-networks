✅ 1. Functions of the Data Link Layer
    Framing (grouping bits into frames)
    Error detection and correction
    Flow control
    Medium Access Control (MAC)
    Addressing via MAC addresses

✅ 2. Framing (Function of Data Link Layer)
🔹 What is Framing?
    Framing is the process of grouping a stream of bits into structured units called frames, so that they can be transmitted and understood correctly.
    Without framing, the receiver wouldn’t know where a message starts or ends.

🔹 How it Works
    The Data Link Layer adds headers and trailers around the data:
    Header: Contains metadata like source/destination MAC addresses, control info.
    Trailer: Often includes error-checking code (like CRC).

This helps:
    Recognize start and end of each frame.
    Provide error detection and addressing.

🔹 Framing Techniques
    Byte Stuffing (Character-Oriented Protocols):
    Uses special characters (like FLAG) to mark frame boundaries.
    If the FLAG appears in data, insert an escape character before it.

Example:
    Data:  Hello FLAG World
    Stuffed: Hello ESC FLAG World
    Bit Stuffing (Bit-Oriented Protocols):

Frame delimiter: a unique bit pattern (e.g., 01111110)
    If sender detects 5 consecutive 1s, it adds a 0 after them in data.
    Receiver removes the extra 0s during decoding.
    Prevents confusion between data and delimiter pattern.

🔹 Why Framing is Important
    | Feature          | Why It Matters                                          |
    | ---------------- | ------------------------------------------------------- |
    | Clear Boundaries | Receiver knows where one frame ends, and another starts |
    | Reliability      | Helps in **error checking** using trailers (like CRC)   |
    | Control          | Ensures proper **flow control** and synchronization     |

✅ 3. Error Detection & Correction (Data Link Layer)
🔹 Error Detection
    Used to detect errors introduced during transmission.

Techniques:
Parity Bit: Adds one bit to make the number of 1s even (even parity) or odd (odd parity).

Checksum: Adds all data bytes; result is sent along. Receiver re-calculates and compares.

CRC (Cyclic Redundancy Check):
    Treats data as a binary number and divides it by a fixed polynomial.
    Remainder (CRC bits) is added to frame.
    Receiver re-divides to check for errors.
    Good for burst error detection.

✅ Error Correction
Ensures that the receiver can fix errors without or with minimal retransmission.

🔹 Hamming Code
    Adds redundant bits to the data.
    Can detect and correct single-bit errors.
    Uses position-based parity checks to locate the exact error bit.

🔹 ARQ (Automatic Repeat reQuest)
    Error control protocol that uses acknowledgments (ACK) and timeouts.
    If receiver detects error or no ACK is received, sender retransmits.

Types:
    Stop-and-Wait ARQ
    Go-Back-N ARQ
    Selective Repeat ARQ

✅ Comparison: Stop-and-Wait vs Go-Back-N vs Selective Repeat
    | Feature                | **Stop-and-Wait ARQ** | **Go-Back-N ARQ**                        | **Selective Repeat ARQ**                |
    | ---------------------- | --------------------- | ---------------------------------------- | --------------------------------------- |
    | **Frames Sent**        | One at a time         | Multiple (within window size)            | Multiple (within window size)           |
    | **ACK**                | After each frame      | Cumulative ACK (for last correct frame)  | Individual ACKs for each frame          |
    | **On Error**           | Resend that frame     | Resend that frame **and all after it**   | Resend **only the erroneous frame**     |
    | **Efficiency**         | Low                   | Medium                                   | High                                    |
    | **Receiver Buffering** | Not needed            | Minimal                                  | Required (to store out-of-order frames) |
    | **Complexity**         | Simple                | Moderate                                 | Complex                                 |
    | **Use Case**           | Simple/slow links     | Faster networks with minor error chances | High-performance, low-error networks    |

✅ 4. Flow Control (Data Link Layer)
🔹 Purpose
    Prevents the sender from sending data faster than the receiver can process, avoiding buffer overflow.

🔹 Techniques
✅ Stop-and-Wait
    Sender sends one frame and waits for ACK.
    Next frame is sent only after acknowledgment.
    Simple but inefficient for high-speed networks.

✅ Sliding Window Protocol
    Sender can send multiple frames (up to a window size) without waiting for ACK.
    Receiver acknowledges received frames.
    Window slides forward as ACKs are received.
    More efficient and widely used.

✅ 5. Access Control / MAC Protocols (Data Link Layer)
🔹 What is MAC?
    Medium Access Control (MAC) determines which device can use the shared communication channel and when, to avoid collisions in a broadcast network like LAN or Wi-Fi.
    Used mainly in the Data Link Layer of networks like Ethernet and Wi-Fi.

🔹 Types of MAC Protocols
✅ 1. ALOHA
Oldest MAC protocol, used in wireless networks.
Pure ALOHA:
    Transmit anytime.
    If collision → wait random time → resend.
    Max efficiency ~18%.

Slotted ALOHA:
    Time is divided into equal slots.
    Transmit only at the beginning of a slot.
    Higher efficiency than Pure ALOHA (~37%).

📌 Drawback: High collision rate due to random transmissions.

✅ 2. CSMA/CD (Carrier Sense Multiple Access with Collision Detection)
    Used in wired networks (e.g., Ethernet).
    Carrier Sense: Device listens to the channel before sending.
    Multiple Access: Many devices use the same channel.
    Collision Detection: If collision is detected, transmission is stopped, and devices wait a random backoff time before retrying.

    🧠 Works well in half-duplex Ethernet but not used in full-duplex or modern switched Ethernet.

✅ 3. CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance)
    Used in Wi-Fi (IEEE 802.11).
    Cannot detect collisions (due to wireless medium), so it tries to avoid them.
    How it works:
    Listens to channel before sending.
    If free, waits for Inter-Frame Space (IFS).
    May send RTS (Request to Send) → receiver replies with CTS (Clear to Send).
    Helps avoid collision with hidden nodes.

📌 Efficient in wireless communication, where collision detection isn’t possible.
    | Protocol      | Used In   | Works How?                               | Collision Handling       | Efficiency     |
    | ------------- | --------- | ---------------------------------------- | ------------------------ | -------------- |
    | Pure ALOHA    | Satellite | Send anytime                             | Detect after             | \~18%          |
    | Slotted ALOHA | Satellite | Send at slot start                       | Detect after             | \~37%          |
    | CSMA/CD       | Ethernet  | Sense → Send → Detect collision          | Retransmit after backoff | Medium-High    |
    | CSMA/CA       | Wi-Fi     | Sense → Wait → Avoid collision (RTS/CTS) | Avoids before sending    | High for Wi-Fi |

✅ 6. LAN Technologies (Data Link Layer)
    | Feature    | **Ethernet**          | **Wi-Fi**               | **Switch**                     |
    | ---------- | --------------------- | ----------------------- | ------------------------------ |
    | Type       | Wired LAN             | Wireless LAN            | LAN Device                     |
    | Protocol   | CSMA/CD               | CSMA/CA                 | No collision; uses MAC table   |
    | Medium     | Cables (twisted pair) | Radio waves             | Ethernet cables                |
    | Addressing | MAC Address           | MAC Address             | Uses MAC table                 |
    | Speed      | Up to 100 Gbps        | Up to 10 Gbps (Wi-Fi 6) | Depends on connected devices   |
    | Security   | Physically secure     | Needs WPA2/WPA3         | Supports VLANs & port security |
    | OSI Layer  | Layer 2               | Layer 2                 | Layer 2 (or Layer 3 for smart) |
    | Use Case   | Offices, labs         | Homes, public networks  | Backbone of LAN infrastructure |


✅ 7. MAC Addressing (Media Access Control Address)
🔹 What is a MAC Address?
A unique identifier assigned to a device’s Network Interface Card (NIC).
Ensures local delivery of data within a LAN (Layer 2 communication).

🔹 Format
48-bit address written in hexadecimal.
Usually shown as:
00:1A:2B:3C:4D:5E (6 pairs of hex digits)

📌 The first 24 bits = OUI (Organizationally Unique Identifier) — identifies the manufacturer.
📌 The last 24 bits = unique device-specific ID.

🔹 Usage
Used by Ethernet, Wi-Fi, and Switches to deliver frames to the correct device.
Works at Data Link Layer (Layer 2)
Switches use MAC addresses to forward data only to the intended port/device.

🔹 Key Points for Interviews
MAC address is hardware-based (burned into NIC).
It is not routable like an IP address.
It ensures point-to-point or broadcast delivery within the same LAN.

✅ 8. Data Link Layer Devices
| **Device**                         | **Description**                                                                                                                                                          |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Switch**                         | Operates at **Layer 2**; forwards frames using **MAC addresses**. Maintains a **MAC address table** to send data only to the correct device. Reduces collisions in LANs. |
| **Bridge**                         | Connects **two LAN segments** at Data Link Layer. Filters traffic based on **MAC addresses** and helps in **segmenting networks**.                                       |
| **NIC** *(Network Interface Card)* | Hardware inside a computer or device that **connects it to a network**. Has a **unique MAC address** and is responsible for **frame transmission and reception**.        |


✅ 9. Switching Techniques (used by Layer 2 Switches)

🔹 1. Store-and-Forward Switching
    The switch receives the entire frame, checks for errors (using CRC), then forwards it.
    Ensures error-free transmission.
    Slower due to full-frame buffering.
    📌 Use Case: When reliability is more important than speed.

🔹 2. Cut-Through Switching
    The switch starts forwarding the frame as soon as it reads the destination MAC address (i.e., doesn’t wait for full frame).
    Faster, but may forward corrupted frames (no error checking).
    📌 Use Case: When speed/low latency is preferred over reliability.

| Type      | Communication | Delivered To              | MAC Address Used                  |
| --------- | ------------- | ------------------------- | --------------------------------- |
| Unicast   | One-to-One    | Specific single device    | Unique MAC address                |
| Multicast | One-to-Group  | Selected group of devices | Multicast MAC (e.g., 01:00:5E...) |
| Broadcast | One-to-All    | All devices in the LAN    | FF\:FF\:FF\:FF\:FF\:FF            |

✅ Dissecting an Ethernet Frame (IEEE 802.3)
An Ethernet frame is the basic unit of data at the Data Link Layer used in wired LANs. It consists of structured fields for addressing, control, data, and error detection.

🧩 Ethernet Frame Structure
| **Field**                       | **Size (Bytes)** | **Description**                                                                   |
| ------------------------------- | ---------------- | --------------------------------------------------------------------------------- |
| **Preamble**                    | 7                | Pattern of `10101010` for **synchronization** between sender and receiver.        |
| **Start Frame Delimiter (SFD)** | 1                | Marks the **start of the frame** (pattern: `10101011`).                           |
| **Destination MAC**             | 6                | **MAC address** of the receiving device.                                          |
| **Source MAC**                  | 6                | **MAC address** of the sending device.                                            |
| **Type / Length**               | 2                | Indicates either the **protocol type** (e.g., IPv4 = 0x0800) or **payload size**. |
| **Payload (Data)**              | 46–1500          | Actual data being sent (e.g., IP packet).                                         |
| **Padding (optional)**          | varies           | If data is < 46 bytes, **padding** is added to meet the **minimum frame size**.   |
| **CRC / FCS**                   | 4                | **Cyclic Redundancy Check** for **error detection**.                              |

Minimum Ethernet frame size: 64 bytes
Maximum frame size: 1518 bytes (excluding jumbo frames)
If errors are detected via CRC, the frame is discarded.

[Preamble][SFD][Dest MAC][Source MAC][Type/Len][Payload][CRC]

