✅ Functions of the Network Layer (Layer 3)
The Network Layer ensures end-to-end delivery of packets across different networks. It plays a crucial role in internet communication and routing.

✅ 1. Logical Addressing
🎯 Purpose:
To uniquely identify every device across a network.
🔑 Address Used:
IP Address (IPv4 like 192.168.1.2 or IPv6 like 2001:db8::1)

🔍 Why Needed:
MAC addresses are local and physical (specific to a device’s NIC).
But to route data across global networks, we need IP addresses.
Logical addressing allows devices on different networks to communicate.

📦 Example:
Sender IP:     192.168.1.2
Receiver IP:   172.217.160.78 (e.g., google.com)

Every data packet must carry the source and destination IP address. Without this, routing won’t work.

✅ 2. Routing
🎯 Purpose:
To determine the best possible path for the packet to travel from source to destination.

⚙️ How It Works:
Routers examine the destination IP.
They use routing tables to decide the best next-hop route.
This happens dynamically at every intermediate router.

📚 Algorithms Used:

Distance Vector – e.g., RIP (Routing Information Protocol)
Link State – e.g., OSPF (Open Shortest Path First)
Hybrid – e.g., EIGRP (Enhanced Interior Gateway Routing Protocol)

📌 Key Point:
Routing adapts in real-time to network changes like link failure or congestion.

✅ 3. Packet Forwarding
🎯 Purpose:
To move the packet from one node (router) to the next until it reaches its destination.

⚙️ How It Works:

At each hop (router), the router:
Looks up the destination IP.
Uses its routing table to choose the next-hop.
Forwards the packet accordingly.

This repeats until the packet reaches the final destination.

📌 Forwarding vs Routing:
Concept	Description
Routing	Decision-making: selects the path.
Forwarding	Actual transfer of packets along the path.

✅ 4. Fragmentation & Reassembly
🎯 Purpose:
To handle data that’s too large for the transmission path (larger than the MTU).

🔨 Fragmentation:
Performed when packet size > MTU.
Happens at source device or intermediate routers.
Packet is split into smaller fragments.

Each fragment includes:
Identification number
Fragment offset
More Fragments (MF) flag

🛠️ Reassembly:
Done at the destination.
Fragments are combined based on:
Offset values
MF flag
If any fragment is lost, entire reassembly fails.

📌 Example:

Suppose MTU = 1500 bytes
If a 4000-byte packet is sent:
It is divided into 3 fragments:
1500 bytes
1500 bytes
1000 bytes


✅ 2. IP Addressing
🔹 IPv4
32-bit address (e.g., 192.168.1.1)
Written in dotted decimal format.
Divided into network and host parts.

🔹 IPv6
128-bit address (e.g., 2001:0db8::1)
Used to overcome IPv4 exhaustion.
Written in hexadecimal and supports more devices.

🔹 IPv4 Address Classes
| Class | Range                       | Default Subnet Mask | Use Case        |
| ----- | --------------------------- | ------------------- | --------------- |
| A     | 0.0.0.0 – 127.255.255.255   | 255.0.0.0           | Large networks  |
| B     | 128.0.0.0 – 191.255.255.255 | 255.255.0.0         | Medium networks |
| C     | 192.0.0.0 – 223.255.255.255 | 255.255.255.0       | Small networks  |
| D     | 224.0.0.0 – 239.255.255.255 | —                   | Multicasting    |
| E     | 240.0.0.0 – 255.255.255.255 | —                   | Research        |
🔹 Public vs Private IPs
Private IP (used in LANs):
Class A: 10.0.0.0 – 10.255.255.255
Class B: 172.16.0.0 – 172.31.255.255
Class C: 192.168.0.0 – 192.168.255.255
Public IP: Routable on the internet, assigned by ISPs.

🔹 Static vs Dynamic IPs
Static IP: Manually assigned, doesn't change.
Dynamic IP: Assigned by DHCP, changes periodically.

🔹 CIDR (Classless Inter-Domain Routing)
Removes dependency on classes (A/B/C).
Uses prefix notation like 192.168.1.0/24.
/24 means 24 bits for network, 8 for hosts.

🧠 Interview Tip
Know how to calculate no. of hosts in a subnet:
Formula:
No. of hosts = 2^(32 - subnet bits) - 2  
Example: /24 → 2^(32-24) - 2 = 254 hosts

✅ 3. Subnetting & Supernetting
🔹 Subnetting
Divides a large network into smaller sub-networks (subnets).
Helps in better IP address management and network isolation.
Uses a subnet mask or CIDR notation (e.g., /24).

📌 Example:
192.168.1.0/24 → can be subnetted into:
192.168.1.0/26, 192.168.1.64/26, etc.

📐 Host Calculation:
Formula: 2^(32 - subnet bits) - 2
Ex: /26 → 2⁶ - 2 = 62 hosts per subnet.

🔹 Supernetting
Combines multiple networks into a larger one.
Used mainly in route aggregation to reduce routing table size.
Often seen in ISP-level routing.

📌 Example:
Combining:
192.168.0.0/24, 192.168.1.0/24 → becomes 192.168.0.0/23

✅ 4. IPv4 Packet Format
🔹 Key Fields
| Field                                      | Description                                                  |
| ------------------------------------------ | ------------------------------------------------------------ |
| **Version**                                | IPv4 = `4`                                                   |
| **Header Length**                          | Size of header in 32-bit words (usually 20 bytes)            |
| **Total Length**                           | Entire packet size (header + data) in bytes                  |
| **TTL (Time To Live)**                     | Limits packet lifetime to avoid infinite loops               |
| **Protocol**                               | Indicates upper layer protocol (e.g., `6` = TCP, `17` = UDP) |
| **Source IP**                              | IP address of sender                                         |
| **Destination IP**                         | IP address of receiver                                       |
| **Checksum**                               | Error checking of header                                     |
| **Identification, Flags, Fragment Offset** | Used for fragmentation & reassembly                          |
🧠 Important Note:
TTL (Time To Live) is decremented by 1 at each hop. If TTL = 0, the packet is discarded → prevents infinite routing loops.

✅ 6. Types of Routing
| **Type**    | **Description**                                                                            |
| ----------- | ------------------------------------------------------------------------------------------ |
| **Static**  | Manually configured routes by network admin.                                               |
| **Dynamic** | Routers **automatically learn** routes using routing protocols (e.g., RIP, OSPF).          |
| **Default** | Used when **no specific route** is found; acts as a **fallback path** (e.g., `0.0.0.0/0`). |

✅ 7. Routing Algorithms
| **Algorithm**       | **Description**                                                                                           |
| ------------------- | --------------------------------------------------------------------------------------------------------- |
| **Distance Vector** | Chooses path based on **hop count** (shortest path). Example: **RIP**                                     |
| **Link State**      | Builds a **full map** of the network and computes best path using Dijkstra’s algorithm. Example: **OSPF** |
| **Path Vector**     | Maintains **path information** with policies, mainly used **between ISPs**. Example: **BGP**              |

✅ 8. Routing Protocols
| **Protocol** | **Type**        | **Description**                                                                                     |
| ------------ | --------------- | --------------------------------------------------------------------------------------------------- |
| **RIP**      | Distance Vector | Uses **hop count** as metric (max 15 hops). Simple but slow.                                        |
| **OSPF**     | Link State      | Builds complete **network topology**. Fast convergence, widely used in enterprises.                 |
| **BGP**      | Path Vector     | Used for **Internet routing** between ISPs (Autonomous Systems). Supports **policy-based routing**. |

✅ 9. NAT (Network Address Translation)
🔹 What is NAT?
NAT translates private IP addresses (used inside a LAN) into a public IP address (used on the internet), allowing devices in a private network to access the internet using a single public IP.

🔹 Why is NAT Used?
Conserves public IP addresses
Provides basic security by hiding internal IPs
Enables multiple devices to share one public IP

🔹 Types of NAT
| **Type**                           | **Description**                                                                   |
| ---------------------------------- | --------------------------------------------------------------------------------- |
| **Static NAT**                     | One-to-one mapping of private IP ↔ public IP                                      |
| **Dynamic NAT**                    | Maps private IPs to a **pool** of public IPs                                      |
| **PAT (Port Address Translation)** | Many-to-one mapping using **ports** to distinguish devices (aka **NAT Overload**) |

🧠 Key Point:
PAT is the most common form of NAT, allowing hundreds of devices to share a single IP using different port numbers.

📌 Example
Private IP: 192.168.1.10 → Public IP: 203.0.113.5:5050  
Another Device: 192.168.1.11 → 203.0.113.5:5051  

🔐 Bonus – Interview Tips
❓ “Does NAT break end-to-end connectivity?”  ✅ Yes, it modifies IP headers, affecting peer-to-peer apps.
❓ “Where is NAT implemented?”   ✅ On routers or firewalls at the network boundary.
❓ “Can NAT be used with IPv6?”  ✅ NAT is not preferred in IPv6 as it offers enough addresses natively.

✅ 10. ARP (Address Resolution Protocol)
🔹 What is ARP?
ARP maps a known IP address to its corresponding MAC address within a local network (LAN).

🔹 Why is it needed?
Devices communicate using MAC addresses at the Data Link Layer.
If a device knows the IP but not the MAC, it sends an ARP Request to find it.

🔹 How it works:
ARP Request:
Broadcasted: "Who has IP 192.168.1.1? Tell me your MAC."

ARP Reply:
The device with that IP replies with its MAC address.
The sender stores the mapping in its ARP cache.

📌 Key Points:
Only works in IPv4 networks.
Operates at Layer 2 (Data Link) but assists Layer 3 (Network).
Used only within the same LAN/subnet — not across routers.

🧠 Interview Tip:
ARP is used when the destination IP is known, but the MAC address is unknown — typical during the first packet transmission.

✅ 11. ICMP (Internet Control Message Protocol)

🔹 What is ICMP?
ICMP is used by network devices (like routers) to send error messages and diagnostic/control information.
It is not used for data transfer, but for network health and troubleshooting.

🔹 Common ICMP Use Cases
| **Use Case**                | **ICMP Type**             | **Description**                        |
| --------------------------- | ------------------------- | -------------------------------------- |
| **Ping**                    | Echo Request / Echo Reply | Tests connectivity between two devices |
| **Destination Unreachable** | Type 3                    | Receiver or network not reachable      |
| **Time Exceeded**           | Type 11                   | TTL expired (used in traceroute)       |
| **Redirect**                | Type 5                    | Suggests a better route to the host    |


📌 Key Points:
ICMP is encapsulated in IP packets (protocol number: 1).
Works with both IPv4 and IPv6 (ICMPv6).
Routers and hosts generate ICMP messages to report network issues.

🧠 Interview Tip:
Ping uses ICMP to measure round-trip time and packet loss.
Traceroute relies on ICMP "Time Exceeded" messages to map the route.

✅ 12. Fragmentation
🔹 What is Fragmentation?
When an IP packet is larger than the MTU (Maximum Transmission Unit) of the network, it is split into smaller fragments for transmission.
Example: If MTU = 1500 bytes and a packet is 4000 bytes → it is fragmented.

🔹 Who handles it?
✅ IP layer (Network Layer) handles fragmentation and reassembly.
Fragmentation: At the sender or an intermediate router
Reassembly: Only at the destination host

🔹 Key IPv4 Header Fields for Fragmentation
| Field                   | Purpose                                                       |
| ----------------------- | ------------------------------------------------------------- |
| **Identification**      | Identifies which fragments belong to the same original packet |
| **Fragment Offset**     | Indicates position of this fragment in the original packet    |
| **More Fragments (MF)** | Bit set to 1 if more fragments follow; 0 if last fragment     |
📌 Example:
A 4000-byte packet over a 1500-byte MTU link → split into 3 fragments:
1st: bytes 0–1499
2nd: bytes 1500–2999
3rd: bytes 3000–3999
🧠 Interview Tip:
Fragmentation is inefficient and should be avoided using Path MTU Discovery.
IPv6 does not allow routers to fragment; only the sender can do it.

✅ 13. Switching Techniques
Switching determines how data moves between devices in a network.

🔹 1. Circuit Switching
Dedicated path is established before transmission.
Resources remain reserved for the entire session.
Example: Traditional telephone networks

📌 Pros: Guaranteed bandwidth, low latency
📌 Cons: Wastes resources if no data is sent

🔹 2. Packet Switching
Data is divided into small packets, sent independently.
Packets may take different routes and are reassembled at the destination.
Example: Internet, IP-based communication

📌 Pros: Efficient, scalable, handles bursty traffic
📌 Cons: May cause delay, jitter, or packet loss

🔹 3. Message Switching
Entire message is stored at each intermediate node before forwarding (Store-and-Forward).
No fixed path or packetization.

📌 Used in: Early telegraph/email systems
📌 Cons: High storage & delay, not suitable for real-time apps

🧠 Interview Tip:
The Internet uses packet switching, not circuit switching.
Circuit switching is more suitable for voice; packet switching for data.

✅ 14. Network Devices (Layer 3)
🔹 Router
Connects different networks (e.g., LAN to Internet).
Uses IP addresses to route packets.
Works at Network Layer (Layer 3) of the OSI model.
Maintains and uses a routing table.

📌 Example: Home Wi-Fi router connecting your LAN to the Internet.

🔹 Layer 3 Switch
A switch with routing capabilities.
Performs routing within a LAN or VLANs.
Faster than routers for internal traffic due to hardware-based routing.

📌 Used in enterprise LANs for inter-VLAN routing.
🧠 Interview Tip:
Router vs Layer 3 Switch:
Both route using IP, but Layer 3 switches are optimized for speed in LANs, while routers are for WAN/internet connectivity.

✅ 15. Tunneling & VPN Basics
🔹 Tunneling
Encapsulates one packet inside another.
Enables data to pass through incompatible networks or bypass restrictions.
Often used to carry private traffic over a public network.

📌 Example: IPv6 packets inside IPv4 using 6to4 tunneling.
🔹 VPN (Virtual Private Network)
Uses tunneling + encryption to securely send data over public networks.
Creates a private, encrypted tunnel between the user and remote network.
Hides IP address and ensures confidentiality & integrity.

📌 Protocols used:
IPSec, PPTP, L2TP, OpenVPN, WireGuard

🧠 Interview Tip:
VPN uses tunneling, but not all tunneling is encrypted. VPN adds encryption, authentication, and integrity checks.

✅ 16. IPv6 Concepts
🔹 Key Features of IPv6
| Feature                | Description                                                        |
| ---------------------- | ------------------------------------------------------------------ |
| **128-bit Addressing** | Supports **2¹²⁸** addresses – solves IPv4 exhaustion               |
| **No NAT Required**    | Every device can have a **unique global address**                  |
| **Simplified Header**  | Fewer fields → faster processing by routers                        |
| **Built-in IPsec**     | Native support for **encryption & authentication**                 |
| **Auto-configuration** | Stateless Address Auto Config (SLAAC) for plug-and-play networking |

🔹 Example IPv6 Address
2001:0db8:85a3:0000:0000:8a2e:0370:7334
📌 Can be shortened to: 2001:db8:85a3::8a2e:370:7334

🧠 Interview Tip:
IPv6 eliminates the need for NAT, supports end-to-end connectivity, and improves QoS & security through IPsec.

✅ 17. Logical Addressing vs Physical Addressing
| **Aspect**                  | **Logical Addressing (IP)**                    | **Physical Addressing (MAC)**                |
| --------------------------- | ---------------------------------------------- | -------------------------------------------- |
| **Type**                    | Software-based                                 | Hardware-based (burned into NIC)             |
| **Changes Across Networks** | ✅ Yes (can be reassigned)                     | ❌ No (fixed per device)                    |
| **OSI Layer**               | Network Layer (Layer 3)                        | Data Link Layer (Layer 2)                    |
| **Format**                  | IPv4: 32-bit / IPv6: 128-bit                   | 48-bit hexadecimal (e.g., `00:1A:2B:3C...`)  |
| **Purpose**                 | Uniquely identifies device **across networks** | Identifies device **within a local network** |
| **Example**                 | `192.168.1.5`                                  | `00:1A:2B:3C:4D:5E`                          |

🧠 Interview Tip:
IP address is temporary and logical, MAC is permanent and physical.
IP is used for routing, MAC is used for local delivery.


