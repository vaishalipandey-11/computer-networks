📘 1.1 Data Communications
🔹 What is Data Communication?
The exchange of data between devices over a medium using hardware + software.

🔹 Characteristics
Delivery: To correct destination.
Accuracy: Without errors.
Timeliness: On-time delivery.
Jitter: Minimized variation in delay (important for media).

🔹 Components
Message: Actual data (text, image, etc.)
Sender/Receiver: Devices involved in transmission.
Medium: Path (e.g., cable, radio waves).
Protocol: Communication rules (e.g., TCP/IP).

🔹 Data Representation

| Type    | Notes                                  |
| ------- | -------------------------------------- |
| Text    | ASCII (7-bit), Unicode (32-bit)        |
| Numbers | Direct binary representation           |
| Image   | Pixels, encoded in B/W, grayscale, RGB |
| Audio   | Analog, converted for transmission     |
| Video   | Frame sequences, also analog/digital   |

📘 Data Flow Modes
| Mode        | Direction                | Example            |
| ----------- | ------------------------ | ------------------ |
| Simplex     | One-way                  | Keyboard → Monitor |
| Half-Duplex | One-at-a-time            | Walkie-talkie      |
| Full-Duplex | Both ways (simultaneous) | Telephone          |

📘 1.2 Networks
🔹 Network
Group of connected devices (nodes) sharing data.

🔹 Distributed Processing
Work is split among multiple systems (vs. centralized).

📘 Network Criteria
Performance: Transit time, response time, throughput, delay.
Reliability: Low failure rate, fast recovery.
Security: Protection against unauthorized access/loss.

📘 Physical Structures
🔹 Connection Types
| Type           | Description                        |
| -------------- | ---------------------------------- |
| Point-to-Point | Dedicated link between two devices |
| Multipoint     | Link shared by multiple devices    |

🔗 Physical Topology
| Topology | Key Points                                               | Use Case        |
| -------- | -------------------------------------------------------- | --------------- |
| Mesh     | Direct links between all nodes. Reliable, costly.        | WANs            |
| Star     | Devices connected to central hub. Scalable.              | LANs            |
| Bus      | Single backbone. Cheap, outdated.                        | Old Ethernet    |
| Ring     | Circular connection. Easy to install, failure sensitive. | Token Ring      |
| Hybrid   | Combo of above. Flexible but complex.                    | Modern networks |

Terms:

Repeater: Boosts signal
Hub: Central connection device
Tap: Connector to backbone
Drop line: Connects device to backbone

🧠 Network Models
| Model  | Layers | Use                          |
| ------ | ------ | ---------------------------- |
| OSI    | 7      | Reference                    |
| TCP/IP | 5      | Practical (used in Internet) |

🌐 Network Types
| Type | Scope               | Notes                             |
| ---- | ------------------- | --------------------------------- |
| LAN  | Small (office/home) | High speed (up to Gbps), private  |
| MAN  | City-wide           | Medium-range, often telecom-based |
| WAN  | Country/global      | Long distance (e.g., Internet)    |

📡 1.3 – The Internet
🌐 What is the Internet?
A global system of interconnected networks enabling communication, data sharing, online transactions, and services like email, research, and streaming.

🧠 Key Terms
| Term         | Meaning                                                            |
| ------------ | ------------------------------------------------------------------ |
| **Network**  | Group of interconnected devices (computers, printers, etc.)        |
| **internet** | A connection between two or more networks                          |
| **Internet** | The global "network of networks" using standard protocols (TCP/IP) |

📜 Brief History
| Year            | Event                                                                             |
| --------------- | --------------------------------------------------------------------------------- |
| **1960s**       | ARPA aimed to connect research computers to share data                            |
| **1967**        | ARPANET proposed with IMP (Interface Message Processor) nodes                     |
| **1969**        | ARPANET launched with 4 nodes: UCLA, UCSB, SRI, Utah                              |
| **Early 1970s** | TCP developed by Vint Cerf & Bob Kahn for reliable communication                  |
| **Later**       | TCP split into TCP (reliable delivery) + IP (routing) = **TCP/IP protocol suite** |

🔄 TCP/IP Overview
| Protocol | Role                                                            |
| -------- | --------------------------------------------------------------- |
| **TCP**  | Ensures reliable data delivery, handles segmentation/reassembly |
| **IP**   | Routes packets to destination (addressing and path selection)   |

🌍 Modern Internet Structure
Decentralized (non-hierarchical) network of networks.
Evolving constantly with private companies as major contributors.

📶 ISP (Internet Service Provider) Hierarchy
| Level                     | Description                                                                    |
| ------------------------- | ------------------------------------------------------------------------------ |
| 🌐 **International ISPs** | Top-level; connect continents and countries                                    |
| 🏢 **National ISPs**      | Large backbone networks (e.g., SprintLink) connected via NAPs & Peering Points |
| 📡 **Regional ISPs**      | Serve cities or large regions; connect to national ISPs                        |
| 🏠 **Local ISPs**         | Directly connect end-users (homes, businesses, universities)                   |

✅ Network Models
🔹 What is a Network?
A combination of hardware (e.g., cables, routers) and software (e.g., email, file transfer protocols) that enables data transmission between devices.

🔹 Why Layered Approach?
Breaks down complex networking into simpler, organized layers.
Follows a top-down flow when sending data and bottom-up when receiving.
📬 Like posting a letter: can't pick it up before it's dropped.

🔹 Key Concepts
Hierarchy: Each layer depends on the one below.
Services: A layer uses services provided by the layer beneath it.
Modularity: Each layer handles a specific responsibility.

🔹 Network Models
| Model      | Layers | Description                                                                   |
| ---------- | ------ | ----------------------------------------------------------------------------- |
| **OSI**    | 7      | Theoretical reference model, not widely used in practice                      |
| **TCP/IP** | 5      | Practical model used on the Internet; forms the backbone of modern networking |
