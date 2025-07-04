🌐 1. HTTP & HTTPS (HyperText Transfer Protocol)
✅ What is HTTP?
Protocol used by web browsers to request and receive web pages.
Stateless: Each request is independent.
Works over port 80.

✅ How It Works:
Client (browser) sends an HTTP request (like GET /index.html).
Server responds with status + data (HTML, CSS, etc.).

✅ Common HTTP Methods:
GET: Retrieve data
POST: Submit data (e.g., login form)
PUT: Update data
DELETE: Remove resource

✅ Status Codes:
200 OK: Success
404 Not Found: Page doesn’t exist
500 Internal Server Error: Server failed

✅ HTTPS:
Secure version of HTTP.
Uses SSL/TLS for encryption.
Works over port 443.

🧠 Interview Tip: Know the TLS handshake basics and how HTTPS ensures confidentiality and authenticity.
| Step                       | Purpose                           | What Happens                                                |
| -------------------------- | --------------------------------- | ----------------------------------------------------------- |
| **Client Hello**           | Start handshake                   | Client sends supported protocols, cipher suites, random no. |
| **Server Hello**           | Select encryption & send identity | Server sends selected cipher + its **digital certificate**  |
| **Certificate Verify**     | Authenticate server               | Client checks if certificate is valid (issued by CA)        |
| **Key Exchange**           | Create shared secret              | Securely exchange key (Diffie-Hellman or RSA)               |
| **Session Key Generation** | Secure communication starts       | Both sides generate same **symmetric session key**          |
| **Finished Message**       | Confirm success                   | Both sides confirm handshake is complete, start encryption  |

🌐 HTTPS Ensures This Security
| Security Property    | How HTTPS Achieves It                                      |
| -------------------- | ---------------------------------------------------------- |
| **Confidentiality**  | Encrypts data using session key (AES, ChaCha20)            |
| **Authenticity**     | Verifies server identity through SSL/TLS certificates      |
| **Integrity**        | Uses MAC (Message Authentication Code) to detect tampering |
| **Encryption Start** | After handshake, all HTTP data is encrypted                |
| **Session Security** | Key is unique per session (Forward Secrecy in TLS 1.3)     |

🔍 2. DNS (Domain Name System)
✅ What DNS Does:
Converts human-readable names (e.g., google.com) to IP addresses (142.250.196.110).
Acts like the phonebook of the internet.

✅ Types of DNS Queries:
Recursive: Client asks DNS server to do all the lookup work and return the final answer.
Iterative: DNS server gives referral to another DNS server closer to the answer.

✅ DNS Records:
A: Maps domain → IPv4 address
AAAA: Maps domain → IPv6 address
MX: Mail exchange (used in email)
CNAME: Alias for another domain

🧠 Interview Tip: Understand the resolution path: Local cache → Recursive resolver → Root → TLD → Authoritative DNS
| **Step**                  | **What Happens**                                                                | **Example for [www.example.com](http://www.example.com)**              |
| ------------------------- | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| **1. Local Cache**        | Browser/OS checks if it already knows the IP.                                   | Found? → Done. Otherwise, go to next step.                             |
| **2. Recursive Resolver** | ISP’s DNS server (or Google DNS, etc.) → does the heavy work of finding the IP. | Queries other DNS servers if needed.                                   |
| **3. Root Server**        | Gives the location of the **TLD server**.                                       | Points to **.com** TLD server.                                         |
| **4. TLD Server**         | Gives the location of the **Authoritative server**.                             | Points to **example.com’s** DNS server.                                |
| **5. Authoritative DNS**  | Knows the actual IP address of the domain.                                      | Responds with the IP of **[www.example.com](http://www.example.com)**. |
| **6. Response Returned**  | Recursive resolver gives the IP back to your browser.                           | Now your browser can load the website.                                 |


🔁 3. FTP vs HTTP
| **Feature**    | **FTP**                          | **HTTP**               |
| -------------- | -------------------------------- | ---------------------- |
| **Purpose**    | File transfer                    | Web page transfer      |
| **Port**       | 20, 21                           | 80 (HTTP), 443 (HTTPS) |
| **Connection** | Stateful                         | Stateless              |
| **Security**   | Unsecure (FTP), FTPS/SFTP secure | Secure over HTTPS      |
| **Usage**      | Upload/download files            | Browse websites / APIs |

🧠 Interview Tip: Know when to use FTP (large file transfers, backups) vs HTTP (web browsing).

📧 4. Email Protocols – SMTP, POP3, IMAP
| **Protocol** | **Purpose**                          | **Works Between**                | **Port**               |
| ------------ | ------------------------------------ | -------------------------------- | ---------------------- |
| **SMTP**     | Send emails                          | Client → Server, Server → Server | 25 (or 587 encrypted)  |
| **POP3**     | Download & remove emails from server | Client → Server                  | 110                    |
| **IMAP**     | Access emails without deleting       | Client ↔ Server                  | 143 (or 993 encrypted) |


🧠 Interview Tip: Know the client-server interaction:
SMTP for sending, IMAP/POP3 for retrieving.

📦 5. DHCP (Dynamic Host Configuration Protocol)
✅ What DHCP Does:
Automatically assigns IP address to devices in a network.
No manual IP configuration required.

✅ DHCP Workflow:
Device sends DHCP Discover
Server replies with DHCP Offer
Client sends DHCP Request
Server sends DHCP Acknowledgement

🧠 Port: UDP 67 (server), UDP 68 (client)

🧠 Interview Tip: DHCP simplifies IP management, especially in large networks (e.g., campus Wi-Fi).

