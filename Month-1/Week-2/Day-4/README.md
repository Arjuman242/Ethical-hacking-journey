# OSI Model – Detailed Notes (Day 2)

## **What is OSI Model?**
The **OSI (Open Systems Interconnection)** model is a **conceptual framework** used to understand and standardize how data is transmitted across a network.  
It divides communication into **7 layers**, where each layer performs a specific role.

**Why OSI Model?**
- To break down complex network communications into simpler steps.
- To ensure interoperability between different devices, systems, and protocols.
- To help engineers debug and design better networking systems.

---

## **7 Layers of OSI Model (Bottom to Top)**

### **1. Physical Layer (Layer 1)**
- **Role:** Deals with physical medium (cables, signals, bits).
- **Examples:** Ethernet cables, fiber optics, Wi-Fi signals.
- **Key Units:** Bits (0s and 1s).

### **2. Data Link Layer (Layer 2)**
- **Role:** Provides error detection, MAC addresses, and frames.
- **Examples:** Switches, ARP, Ethernet frames.
- **Key Units:** Frames.
- **Key Protocols:** PPP, Ethernet.

### **3. Network Layer (Layer 3)**
- **Role:** Responsible for routing data between devices.
- **Examples:** IP (IPv4/IPv6), Routers.
- **Key Units:** Packets.
- **Key Protocols:** ICMP, IP.

### **4. Transport Layer (Layer 4)**
- **Role:** Ensures complete, error-free data delivery.
- **Examples:** TCP, UDP.
- **Key Units:** Segments (TCP) / Datagrams (UDP).
- **Key Protocols:** TCP, UDP.

### **5. Session Layer (Layer 5)**
- **Role:** Manages sessions (connections) between devices.
- **Examples:** Remote Procedure Calls (RPC), NetBIOS.

### **6. Presentation Layer (Layer 6)**
- **Role:** Data translation, encryption, and compression.
- **Examples:** JPEG, PNG, SSL/TLS.

### **7. Application Layer (Layer 7)**
- **Role:** Provides network services to end-users.
- **Examples:** HTTP, FTP, SMTP, DNS.

---

## **Packet Flow Example**
When you open a website:
1. Application Layer: Your browser sends an HTTP GET request.
2. Transport Layer: HTTP request is broken into TCP segments.
3. Network Layer: Each TCP segment is converted into packets with IP addresses.
4. Data Link Layer: Packets are turned into frames.
5. Physical Layer: Frames are converted to signals sent over the cable/Wi-Fi.

---

## **Tools and OSI Layers**
- **Ping:** Works at Network Layer (Layer 3).
- **HTTP:** Works at Application Layer (Layer 7).
- **Wireshark:** Can analyze traffic across multiple OSI layers.

---

