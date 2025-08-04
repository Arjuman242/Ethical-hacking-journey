# Day 6 – Wireshark Lab

## Purpose
To visualize how data moves across the network, focusing on:
- HTTP packet structure
- TCP handshake (connection establishment)
- Layer encapsulation in real traffic

---

## Process & Observations

### Step 1: Capturing HTTP Packets
- Started Wireshark on the active network interface.
- Applied filter: `http`.
- Opened example.com and captured the GET request.
- Observed:
  - **Request Line:** `GET / HTTP/1.1`
  - **Response Code:** `200 OK`
  - **Headers:** Host, User-Agent, Content-Type, etc.

### Step 2: Understanding the TCP Handshake
- Applied filter: `tcp`.
- Observed the handshake sequence:
  1. **SYN** – Client initiates the connection.
  2. **SYN-ACK** – Server acknowledges and responds.
  3. **ACK** – Client confirms, completing the handshake.
- Visualized sequence numbers and acknowledgment numbers changing.

### Step 3: Mapping to OSI & TCP/IP Layers
- **Ethernet Header:** Layer 2 (MAC addresses).
- **IP Header:** Layer 3 (Source & Destination IPs).
- **TCP Header:** Layer 4 (Ports, Flags like SYN/ACK).
- **HTTP Data:** Layer 7 (Application layer).

---

## Key Learnings
- Wireshark reveals *real-world networking*, not just theory.
- TCP handshake ensures reliable connection setup before data transfer.
- HTTP operates on top of TCP; encapsulation matches the OSI model flow.

---

## Output
- `wireshark_screenshot.png` – Highlighting TCP handshake and HTTP GET.
- `wireshark_notes.md` – Detailed explanation of headers & observations.
