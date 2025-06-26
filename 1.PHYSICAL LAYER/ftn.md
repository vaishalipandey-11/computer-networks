1. Function of the Physical Layer
The lowest layer of the OSI model.
Its job is to transmit raw bits (0s and 1s) from sender to receiver over a physical medium (like wires or air).
It doesn't care about what the bits mean—only that they are sent and received correctly.

Key Functions:

Define the voltage levels for 0 and 1
Handle bit synchronization
Define cables, connectors, pin layouts
Manage physical transmission methods (optical, electrical, etc.)

2. Data Transmission Modes
This defines how data travels between devices.
| Mode            | Description                         | Example        |
| --------------- | ----------------------------------- | -------------- |
| **Simplex**     | One-way only                        | TV Broadcast   |
| **Half-Duplex** | Two-way, but one side at a time     | Walkie-Talkies |
| **Full-Duplex** | Two-way, simultaneous communication | Phone calls    |

🧠 Interview Tip: Full-duplex doubles speed in both directions — used in modern Ethernet.

3. Types of Transmission
1. Analog vs Digital
Analog: Continuous signal (e.g., human voice)
Digital: Discrete binary values (0s and 1s)

2. Baseband vs Broadband
Baseband: Sends one signal at a time (e.g., Ethernet)
Broadband: Multiple signals sent using multiple frequencies (e.g., Cable TV)

3. Serial vs Parallel
Serial: Bits sent one at a time in a line (less errors, longer distances
Parallel: Bits sent in groups (faster but prone to interference)

4. Transmission Media
🧵 Twisted Pair Cable
Common for LANs (Ethernet)
Inexpensive, moderate speed

Types: UTP (Unshielded), STP (Shielded)

📺 Coaxial Cable
Used in cable TV, older networks
More shielding than twisted pair

💡 Fiber Optic Cable
Uses light (not electricity)
High speed, long distance, no interference

🌐 Wireless Media
Radio waves: Wi-Fi, Bluetooth
Microwaves: Satellite, cellular
Infrared: Remote controls

5. Bandwidth & Throughput
Bandwidth: Max amount of data the channel can carry (measured in bits/sec).
Throughput: Actual rate of successful data transfer.

🧠 Example: Bandwidth is the pipe size; Throughput is how much water flows.

6. Multiplexing Techniques
Multiplexing = Sharing one channel among multiple signals

| Type    | Description                                          | Example           |
| ------- | ---------------------------------------------------- | ----------------- |
| **FDM** | Divides bandwidth into frequency bands               | Radio, TV         |
| **TDM** | Divides time into slots                              | Digital telephony |
| **WDM** | Used in fiber optics (multiple wavelengths of light) | Optical networks  |

🧠 In TDM: Each user gets a fixed time slot in rotation.

7. Encoding Techniques
Used to represent binary 0s and 1s on transmission media:

NRZ (Non-Return to Zero):
High = 1, Low = 0
Simple but no sync

Manchester Encoding:
Transition in middle of each bit
Better synchronization

Differential Manchester:
Uses change in transition to represent bits

🧠 Needed for reliable bit recovery at the receiver

8. Bit Rate vs Baud Rate
Bit Rate: No. of bits transmitted per second (bps)
Baud Rate: No. of signal units per second

⚠️ Bit rate ≠ Baud rate always
If each signal carries 2 bits, then:
Bit rate = 2 × Baud rate

9. Signals – Analog vs Digital
Analog Signal: Continuous (sine wave)
Digital Signal: Discrete levels (square wave)

🧠 Important Terms:

Attenuation: Signal weakening over distance
Noise: Unwanted interference
Latency: Delay in transmission