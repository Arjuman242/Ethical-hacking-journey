# 🛰️ Day 2 – OSI Model + Packet Flow (Week 2 – Networking)

## 📚 What I Learned

### 🔹 OSI Model: The 7 Layers

The **OSI Model (Open Systems Interconnection)** helps standardize the functions of a telecommunication or computing system without regard to its underlying internal structure and technology.

| Layer | Name            | Function                              | Protocol Examples      |
|-------|------------------|----------------------------------------|-------------------------|
| 7     | Application      | Network process to application         | HTTP, FTP, DNS          |
| 6     | Presentation     | Data format, encryption                | SSL, JPEG, MPEG         |
| 5     | Session          | Interhost communication                | NetBIOS, RPC            |
| 4     | Transport        | End-to-end connections and reliability | TCP, UDP                |
| 3     | Network          | Path determination, IP addressing      | IP, ICMP, OSPF          |
| 2     | Data Link        | MAC addressing, error detection        | Ethernet, PPP, ARP      |
| 1     | Physical         | Bits, cables, hardware                 | Wi-Fi, Cables, Hubs     |

---

## 🔧 Practical Tasks

### ✅ Task 1: OSI Diagram Creation
- Created a custom diagram mapping tools and protocols to OSI layers.
- Mapped `ping` to Layer 3, `HTTP` to Layer 7, etc.


### ✅ Task 2: Layer Identification via Tools
- Explored tools like browser dev tools and command-line utilities (`ping`, `curl`) to identify which layer they operate at.

---

## 🧾 Summary Notes

- OSI model helps isolate issues and understand how networking works.
- Layer abstraction is important for modular troubleshooting.
- Real-world protocols can map to more than one layer logically.

---


