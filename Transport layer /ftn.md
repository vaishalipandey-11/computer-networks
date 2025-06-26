✅ 1. Functions of the Transport Layer
| **Function**                         | **Description**                                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------------------------------- |
| **Process-to-Process Communication** | Enables data transfer between specific **applications** on different devices using **port numbers**. |
| **Segmentation & Reassembly**        | Breaks data into **segments** at sender, reassembles them at receiver in correct order.              |
| **Flow Control**                     | Prevents sender from sending too fast for the receiver to handle (e.g., **sliding window**).         |
| **Error Control**                    | Ensures **reliable delivery** via acknowledgments, checksums, and retransmissions.                   |
| **Connection Management**            | Handles **connection setup, maintenance, and teardown** (e.g., **TCP 3-way handshake**).             |

✅ 2. TCP vs UDP
| **Aspect**                    | **TCP (Transmission Control Protocol)**             | **UDP (User Datagram Protocol)**          |
| ----------------------------- | --------------------------------------------------- | ----------------------------------------- |
| **Type**                      | Connection-oriented                                 | Connectionless                            |
| **Reliability**               | ✅ Reliable (uses ACKs, retransmissions)             | ❌ Unreliable (no delivery guarantee)      |
| **Ordering**                  | ✅ Maintains order of data                           | ❌ No ordering                             |
| **Error Checking**            | ✅ Yes (checksum + correction via retransmission)    | ✅ Yes (checksum only, no correction)      |
| **Speed**                     | Slower (due to overhead of reliability)             | Faster (lightweight)                      |
| **Overhead**                  | High                                                | Low                                       |
| **Use Cases**                 | Web (HTTP/HTTPS), Email (SMTP), File Transfer (FTP) | Video streaming, VoIP, DNS, online gaming |
| **Header Size**               | 20–60 bytes (with options)                          | 8 bytes                                   |
| **Flow & Congestion Control** | ✅ Yes                                               | ❌ No                                      |
| **Protocol Number**           | 6                                                   | 17                                        |
🧠 Interview Tip:
Use TCP when reliability & order matter.
Use UDP when speed & low overhead are more important.

✅ TCP vs UDP – Real-Life Use Cases
| **Scenario**                     | **Why TCP? / Why UDP?**                                                    | **Protocol Used** |
| -------------------------------- | -------------------------------------------------------------------------- | ----------------- |
| **Web Browsing (HTTP/HTTPS)**    | Needs reliable & ordered data delivery for loading pages correctly         | **TCP**           |
| **File Transfers (FTP, SFTP)**   | Accuracy is crucial — no data loss allowed                                 | **TCP**           |
| **Email (SMTP, IMAP, POP3)**     | Emails must be delivered reliably and in full                              | **TCP**           |
| **Video Calls (Zoom, Meet)**     | Real-time, minor data loss acceptable to maintain speed                    | **UDP**           |
| **Online Gaming**                | Low latency is critical; missing a few packets is okay                     | **UDP**           |
| **Streaming (Netflix, YouTube)** | Uses **UDP** under the hood (with buffering & error handling at app level) | **UDP**           |
| **DNS Queries**                  | Simple request/response – speed > reliability                              | **UDP**           |
| **VoIP (e.g., WhatsApp call)**   | Real-time conversation – prioritize speed, tolerate some loss              | **UDP**           |
| **Downloading a PDF**            | Must be 100% accurate and complete                                         | **TCP**           |

✅ 3. TCP 3-Way Handshake (Connection Establishment)
🔹 Purpose
To establish a reliable connection between a client and server before data transfer begins.

🔹 Steps
| **Step** | **Sender (Client)**                                                      | **Receiver (Server)**                       |
| -------- | ------------------------------------------------------------------------ | ------------------------------------------- |
| 1️⃣      | **SYN** → Client sends SYN (synchronize) with an initial sequence number | —                                           |
| 2️⃣      | —                                                                        | **SYN-ACK** → Server replies with SYN + ACK |
| 3️⃣      | **ACK** → Client sends ACK to confirm                                    | Connection is established                   |

Client                     Server
  | ---- SYN  ------------> |
  | <--- SYN + ACK -------- |
  | ---- ACK  ------------> |


🧠 Interview Tip:
TCP 3-way handshake ensures both parties agree on initial sequence numbers and are ready for full-duplex communication.

✅ 4. TCP Connection Termination (4-Way Handshake)
🔹 Purpose
To gracefully close a TCP connection between client and server.

🔹 Steps
| **Step** | **Sender**                                    | **Receiver**               |
| -------- | --------------------------------------------- | -------------------------- |
| 1️⃣      | **FIN** → Sends request to terminate its side | —                          |
| 2️⃣      | —                                             | **ACK** → Acknowledges FIN |
| 3️⃣      | **FIN** → Sends FIN to close its side         | —                          |
| 4️⃣      | —                                             | **ACK** → Acknowledges FIN |
Client                     Server
  | ---- FIN -------------> |
  | <--- ACK -------------- |
  | <--- FIN -------------- |
  | ---- ACK -------------> |

Unlike connection setup, termination takes 4 steps because each direction must be closed independently.
The side initiating FIN enters FIN-WAIT states.
The other side enters TIME-WAIT after sending final ACK to ensure all packets are received.

✅ 5. Port Numbers
🔹 What are Port Numbers?
Port numbers identify specific processes/services running on a device, enabling process-to-process communication at the Transport Layer.

🔹 Port Ranges
| **Range**         | **Type**              | **Example**                                   |
| ----------------- | --------------------- | --------------------------------------------- |
| **0 – 1023**      | Well-known ports      | HTTP (80), HTTPS (443), FTP (21)              |
| **1024 – 49151**  | Registered ports      | MySQL (3306), Postgres (5432)                 |
| **49152 – 65535** | Dynamic/Private ports | Used temporarily by clients (ephemeral ports) |

🔹 Common Well-Known Port Numbers
| **Protocol/Service** | **Port Number** |
| -------------------- | --------------- |
| HTTP                 | 80              |
| HTTPS                | 443             |
| FTP                  | 21              |
| SSH                  | 22              |
| DNS                  | 53              |
| SMTP (Email)         | 25              |
| POP3 (Email)         | 110             |
| IMAP (Email)         | 143             |
| DHCP                 | 67, 68          |
| Telnet               | 23              |
| SNMP                 | 161             |

🧠 Interview Tip:
Port + IP = Socket → Uniquely identifies a specific connection between devices.
TCP/UDP both use port numbers, but serve different types of communication.

✅ 6. Segmentation & Reassembly
🔹 Segmentation
Performed by the Transport Layer (TCP/UDP) at the sender’s side.
Large data from the application layer is broken into smaller segments.
Each segment includes a sequence number to help with correct reordering.

📌 Why? → Networks have a limit on packet size (MTU), so data must be split.

🔹 Reassembly
Performed at the receiver’s Transport Layer.
Segments are reordered and combined using sequence numbers to reconstruct the original message.

🧠 Interview Tip:
In TCP, segmentation allows reliable and ordered delivery, and reassembly ensures the original message is accurately reconstructed.

✅ 7. Flow Control – Complete Breakdown

🔹 What is Flow Control?
Flow control is a Transport Layer mechanism that regulates the rate of data transmission between sender and receiver to ensure:
Receiver’s buffer doesn't overflow
Efficient and reliable communication
Minimal retransmissions

🔸 Types of Flow Control
✅ 1. Stop-and-Wait Flow Control
| Aspect       | Description                                                             |
| ------------ | ----------------------------------------------------------------------- |
| How it works | Sender sends **one frame**, waits for **ACK** before sending the next   |
| Use case     | Simple systems where reliability > speed                                |
| Pros         | Easy to implement                                                       |
| Cons         | Wastes bandwidth (inefficient for long-distance or high-speed networks) |

✅ 2. Sliding Window Flow Control
| Aspect             | Description                                                                   |
| ------------------ | ----------------------------------------------------------------------------- |
| How it works       | Sender can send **multiple frames** before needing an ACK (up to window size) |
| Window Size        | Determines how many frames can be sent without waiting for an ACK             |
| Dynamic Adjustment | Receiver can adjust window size (TCP’s `rwnd`)                                |
| Use case           | Widely used in **TCP** for efficient transmission                             |

🔸 Subtypes of Sliding Window:
| Subtype                  | Description                                                    |
| ------------------------ | -------------------------------------------------------------- |
| **Go-Back-N ARQ**        | If an error occurs, **retransmit from the error frame onward** |
| **Selective Repeat ARQ** | Only **retransmit the specific lost/damaged frame**            |

✅ 3. Credit-Based Flow Control
| Aspect       | Description                                                         |
| ------------ | ------------------------------------------------------------------- |
| How it works | Receiver gives sender a **credit** (number of frames it can accept) |
| Seen in      | High-performance or hardware-based networks (e.g., Fibre Channel)   |

🔸 Flow Control in TCP (Practical Focus)
| Feature                     | Role in TCP                                                      |
| --------------------------- | ---------------------------------------------------------------- |
| **Sliding Window Protocol** | Primary mechanism for TCP flow control                           |
| **rwnd (Receiver Window)**  | Advertised by receiver to tell how much it can handle            |
| **Window Scaling**          | Allows window size > 64KB for high-speed networks (RFC 7323)     |
| **ACK-based Control**       | TCP uses ACKs to manage what data has been successfully received |

🧠 Interview Tips
Flow control ≠ congestion control
→ Flow control is end-to-end; congestion control is network-wide

Window size determines throughput
→ Larger window = more data in transit = higher throughput (if receiver supports it)

Selective Repeat > Go-Back-N in terms of bandwidth efficiency
→ But it's more complex to implement

✅ 8. Error Control – Full Breakdown
🔹 What is Error Control?
Error Control is a mechanism at the Transport Layer (also used in Data Link Layer) to:
Detect errors in transmitted data
Correct them (if possible)
Ensure reliable data transfer between sender and receiver

🔸 Types of Error Control
✅ 1. Error Detection
Used to identify if an error has occurred during transmission.

| **Technique**                     | **Description**                                                                |
| --------------------------------- | ------------------------------------------------------------------------------ |
| **Parity Bit**                    | Adds a single bit to make total number of 1s even/odd (simple, not robust)     |
| **Checksum**                      | Adds all data bytes and sends the sum; receiver recomputes to check integrity  |
| **Cyclic Redundancy Check (CRC)** | Uses polynomial division for robust error detection (used in Ethernet, 802.11) |
| **Hamming Code (detection only)** | Can detect 2-bit errors, single-bit correction                                 |

📌 Used in protocols like TCP/IP, Ethernet, and Wi-Fi

✅ 2. Error Correction
Used to locate and fix errors without retransmission.

| **Technique**                      | **Description**                                                         |
| ---------------------------------- | ----------------------------------------------------------------------- |
| **Automatic Repeat reQuest (ARQ)** | Common in Transport Layer – detects error & **requests retransmission** |
| **Forward Error Correction (FEC)** | Adds redundant data for receiver to **auto-correct errors**             |
| **Hamming Code**                   | Also capable of **single-bit correction** using redundant bits          |

🔸 ARQ (Automatic Repeat reQuest) – Subtypes
These are key Error Control protocols used in reliable transport systems (like TCP):

A| **ARQ Type**             | **Description**                                                              |
| ------------------------ | ---------------------------------------------------------------------------- |
| **Stop-and-Wait ARQ**    | Sender waits for ACK after every frame; retransmits if NACK or timeout       |
| **Go-Back-N ARQ**        | Sender continues sending but **retransmits from lost frame onward** on error |
| **Selective Repeat ARQ** | Only the **lost or corrupted frame** is resent                               |

📌 Used in TCP (Selective Repeat behavior) and Data Link protocols like HDLC.

🔸 Error Control in TCP
| **TCP Feature**              | **Role**                                                               |
| ---------------------------- | ---------------------------------------------------------------------- |
| **Checksum**                 | Used in header & data to detect errors                                 |
| **ACKs & NACKs**             | ACK confirms success; missing ACK implies error                        |
| **Timeout & Retransmission** | If ACK not received within timeout → retransmit                        |
| **Sequence Numbers**         | Help reassemble data in order & detect missing segments                |
| **Sliding Window + SACK**    | TCP can implement **Selective Acknowledgments** for efficient recovery |

🧠 Interview Tips:
Detection ≠ Correction: Detection finds the problem, correction fixes it
ARQ is reactive, FEC is proactive
TCP uses error detection (checksum) + retransmission (ARQ) → not FEC

✅ 9. Congestion Control 

🔹 What is Congestion Control?
Congestion Control is a mechanism used (primarily in the Transport Layer, especially TCP) to prevent too much data from being injected into the network, which can lead to:
Packet loss
Delays
Retransmissions
Network collapse

📌 It ensures that the sender adapts its sending rate based on current network conditions.

🔸 Types of Congestion Control Techniques
✅ 1. Open-Loop Congestion Control (Prevention)
Try to prevent congestion before it happens.

| **Technique**            | **Description**                                                                |
| ------------------------ | ------------------------------------------------------------------------------ |
| **Traffic Shaping**      | Controls the rate at which packets are sent (e.g., leaky bucket, token bucket) |
| **Admission Control**    | Denies new connections if the network is near overload                         |
| **Resource Reservation** | Reserves bandwidth before sending data                                         |


✅ 2. Closed-Loop Congestion Control (Reactive)
Responds to congestion after it is detected.

| **Technique**          | **Description**                                                                     |
| ---------------------- | ----------------------------------------------------------------------------------- |
| **Backpressure**       | Upstream node stops sending when downstream is congested (used in virtual circuits) |
| **Choke Packet**       | A special packet sent to inform the sender to slow down                             |
| **Implicit Signaling** | Sender detects congestion indirectly (e.g., packet loss, delay)                     |
| **Explicit Signaling** | Router explicitly informs sender (e.g., ECN bit in IP header)                       |

🔸 TCP Congestion Control (Most Important for Interviews)
TCP uses a closed-loop congestion control strategy with 4 phases:

| **Phase**                    | **Description**                                                             |
| ---------------------------- | --------------------------------------------------------------------------- |
| 1️⃣ **Slow Start**           | Starts with a small congestion window (cwnd), **doubles cwnd each RTT**     |
| 2️⃣ **Congestion Avoidance** | After threshold (ssthresh), **increase cwnd linearly** to avoid overload    |
| 3️⃣ **Fast Retransmit**      | If **3 duplicate ACKs** are received → assume packet loss, retransmit early |
| 4️⃣ **Fast Recovery**        | Reduces cwnd (usually half), avoids going back to slow start immediately    |

📌 Key TCP Variables
| **Variable** | **Meaning**                                           |
| ------------ | ----------------------------------------------------- |
| `cwnd`       | Congestion Window (controls how much can be sent)     |
| `ssthresh`   | Slow Start Threshold (controls when to switch phases) |
| `rwnd`       | Receiver Window (used for **flow control**)           |

🧠 Interview Tip:
TCP congestion control is adaptive, based on network feedback like packet drops or delayed ACKs.
It balances efficiency and fairness among multiple flows.

📌 Real-life Analogy:
Imagine a highway:
Slow Start = one car enters, then 2, then 4...
Congestion Avoidance = adding 1 more car at a time
Fast Retransmit = if a car gets stuck, send a tow truck quickly
Fast Recovery = reduce number of cars temporarily to ease the jam

✅ 10. Header Formats
🔹 1. IPv4 Header Format
| **Field**               | **Description**                                                  |
| ----------------------- | ---------------------------------------------------------------- |
| Version                 | IP version (4 bits, value = 4 for IPv4)                          |
| Header Length           | Length of header in 32-bit words                                 |
| Total Length            | Entire packet size (header + data)                               |
| Identification          | Unique ID for fragmentation                                      |
| Flags & Fragment Offset | Used for fragmentation and reassembly                            |
| TTL (Time to Live)      | Limits packet lifetime to avoid infinite loops                   |
| Protocol                | Indicates the transport layer protocol (e.g., 6 = TCP, 17 = UDP) |
| Header Checksum         | Error-checking for header only                                   |
| Source IP Address       | IP address of sender                                             |
| Destination IP Address  | IP address of receiver                                           |
| Options (optional)      | For special control/data                                         |

📌 Minimum size: 20 bytes (without options)

🔹 2. TCP Header Format
| **Field**             | **Description**                            |
| --------------------- | ------------------------------------------ |
| Source Port           | Port number of sender                      |
| Destination Port      | Port number of receiver                    |
| Sequence Number       | Byte number of first byte in this segment  |
| Acknowledgment Number | Next expected byte (used for ACKs)         |
| Data Offset           | Header length in 32-bit words              |
| Flags (Control bits)  | URG, ACK, PSH, RST, SYN, FIN               |
| Window Size           | Flow control (receiver buffer size)        |
| Checksum              | Error detection for header + data          |
| Urgent Pointer        | Points to urgent data (if URG flag is set) |
| Options (optional)    | MSS, window scaling, timestamps, etc.      |

📌 Minimum size: 20 bytes

🔹 3. UDP Header Format
| **Field**        | **Description**             |
| ---------------- | --------------------------- |
| Source Port      | Port number of sender       |
| Destination Port | Port number of receiver     |
| Length           | Length of UDP header + data |
| Checksum         | Optional error checking     |

📌 Size: 8 bytes (fixed)

🧠 Interview Tips:
IPv4 Header: TTL prevents infinite loops; Protocol field tells if it’s TCP or UDP.
TCP Header: Sequence & ACK numbers + flags = reliable delivery
UDP Header: Minimal overhead, faster, but no reliability

✅ 11. Multiplexing & Demultiplexing
🔹 What is Multiplexing?
Multiplexing is the process of combining multiple application data streams into a single stream for transmission over a shared network.
📌 Happens at the sender side.

🔹 What is Demultiplexing?
Demultiplexing is the process of separating the combined stream back into individual data streams and delivering them to the correct applications.
📌 Happens at the receiver side.

🔹 How It Works in TCP/UDP:
| **Concept**          | **Explanation**                                                                             |
| -------------------- | ------------------------------------------------------------------------------------------- |
| **Identifiers Used** | IP address + Port number (together form a **Socket**)                                       |
| **TCP/UDP Role**     | Use port numbers to identify the correct **process** on the destination machine             |
| **Example**          | Receiving system uses the **destination port number** to direct the data to the correct app |
