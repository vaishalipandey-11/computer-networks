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

🔁 3. FTP vs HTTP
Feature	FTP	HTTP
Purpose	File Transfer Protocol	Web page transfer
Ports	20, 21	80 (HTTP), 443 (HTTPS)
Connection	Stateful (maintains session)	Stateless (no memory)
Security	Unsecure (FTP)	Secure (HTTPS)

🧠 Interview Tip: Know when to use FTP (large file transfers, backups) vs HTTP (web browsing).

📧 4. Email Protocols – SMTP, POP3, IMAP
✅ SMTP (Simple Mail Transfer Protocol)
Used for sending emails.
Works between client → server, and server → server.
Port: 25 (or 587 with encryption)

✅ POP3 (Post Office Protocol v3)
Used to download emails to local computer.
Deletes mail from server after download.
Port: 110

✅ IMAP (Internet Message Access Protocol)
Accesses emails directly from the server.
Allows multi-device sync (like Gmail app + desktop).
Port: 143 (or 993 for encrypted)

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

