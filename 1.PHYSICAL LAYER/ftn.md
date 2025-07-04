# 📡 Physical Layer – OSI Model

The **Physical Layer** is the lowest layer of the OSI model.  
It transmits **raw bits (0s and 1s)** over a physical medium like wires or air.  
⚙️ It does **not interpret the meaning of the bits**, it just sends them correctly.

---

## 🔑 Key Functions
- ⚡ **Decide how voltage represents 0 or 1.**
- 🔄 **Ensure sender & receiver are in sync to recognize each bit.**
- 🔌 **Define hardware parts like cables, connectors, pins.**
- 🌐 **Handle types of transmission:** electrical signals, light pulses, or radio waves.

---

## 🚦 Data Transmission Modes

| Mode        | Description                          | Example         |
|-------------|--------------------------------------|-----------------|
| Simplex     | One-way only                         | TV Broadcast    |
| Half-Duplex | Two-way, but one side at a time      | Walkie-Talkies  |
| Full-Duplex | Two-way, simultaneous communication  | Phone calls     |

💡 **Interview Tip:** Full-Duplex doubles speed in both directions — used in modern Ethernet.

---

## 🔄 Types of Transmission

### Analog vs Digital
- **Analog:** Continuous signal (e.g., human voice)
- **Digital:** Discrete binary values (0s and 1s)

### Baseband vs Broadband
- **Baseband:** Sends one signal at a time (e.g., Ethernet)
- **Broadband:** Multiple signals sent using multiple frequencies (e.g., Cable TV)

### Serial vs Parallel
- **Serial:** Bits sent one at a time (less errors, longer distances)
- **Parallel:** Bits sent in groups (faster but prone to interference)

---

## 🌐 Transmission Media

### 🧵 Twisted Pair Cable
- Common for LANs (Ethernet)
- Inexpensive, moderate speed
- Types: **UTP (Unshielded)**, **STP (Shielded)**

### 📺 Coaxial Cable
- Used in cable TV, older networks
- More shielding than twisted pair

### 💡 Fiber Optic Cable
- Uses light (not electricity)
- High speed, long distance, no interference

### 🌐 Wireless Media
- **Radio waves:** Wi-Fi, Bluetooth
- **Microwaves:** Satellite, cellular
- **Infrared:** Remote controls

---

## 📊 Bandwidth & Throughput

- **Bandwidth:** Max amount of data the channel can carry (**bits/sec**)
- **Throughput:** Actual rate of successful data transfer

💡 **Example:** Bandwidth is the pipe size; Throughput is how much water flows.

---

## ➗ Multiplexing Techniques

| Type | Description                              | Example         |
|------|------------------------------------------|-----------------|
| FDM  | Divides bandwidth into frequency bands   | Radio, TV       |
| TDM  | Divides time into slots                  | Digital telephony |
| WDM  | Multiple wavelengths of light in fiber optics | Optical networks |

💡 **In TDM:** Each user gets a fixed time slot in rotation.

---

## 🔢 Encoding Techniques

Used to represent binary 0s and 1s on transmission media:

- **NRZ (Non-Return to Zero):** High = 1, Low = 0 → Simple but no sync
- **Manchester Encoding:** Transition in the middle of each bit → Better synchronization
- **Differential Manchester:** Uses change in transition to represent bits

💡 **These are needed for reliable bit recovery at the receiver.**

---

## ⚙️ Bit Rate vs Baud Rate

| Term      | Meaning                                      |
|-----------|----------------------------------------------|
| Bit Rate  | No. of bits transmitted per second (bps)    |
| Baud Rate | No. of signal units per second              |

⚠️ Bit rate ≠ Baud rate always.  
If each signal carries 2 bits, then:  
**Bit rate = 2 × Baud rate**

---

## 🔊 Signals – Analog vs Digital

| Type          | Nature of Signal  | Example        |
|---------------|-------------------|----------------|
| Analog Signal | Continuous (sine wave) | Human voice |
| Digital Signal| Discrete levels (square wave) | Computer data |

---

## 🧠 Important Terms

| Term         | Description                             |
|--------------|-----------------------------------------|
| Attenuation  | Signal weakening over distance          |
| Noise        | Unwanted interference                   |
| Latency      | Delay in transmission                   |

---
