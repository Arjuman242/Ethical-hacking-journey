# 🕵️ Day 1 – Week 3: Wireshark Basics & Packet Analysis  

## 📌 Overview  
This session was focused on **Wireshark** – a powerful tool for capturing and analyzing network traffic.  
We explored how to view and analyze **TCP**, **UDP**, and **DNS queries**, and how to detect problems such as **packet loss** and identify whether an issue comes from the **client** or the **server**.  

---

## 🔎 What I Learned  

### 1. TCP Packets  
- TCP is **connection-oriented** (3-way handshake: SYN → SYN-ACK → ACK).  
- Used by protocols like **HTTP, HTTPS, FTP, SMTP**.  
- **In Wireshark:**  
  - Filter → `tcp`  
  - Look for flags (SYN, ACK, FIN, RST).  
  - Check for **retransmissions** → may indicate packet loss.  

### 2. UDP Packets  
- UDP is **connectionless** (no handshake, faster but less reliable).  
- Common in **DNS, VoIP, streaming**.  
- **In Wireshark:**  
  - Filter → `udp`  
  - Simpler headers, no handshakes.  
  - Loss is harder to detect, often visible in app behavior.  

### 3. DNS Queries  
- DNS translates **domain names → IP addresses**.  
- Usually uses **UDP (port 53)**, sometimes TCP.  
- **In Wireshark:**  
  - Filter → `dns`  
  - Look at **Standard query** and **Response**.  
  - Delays or missing responses → cause browsing issues.  

---

## 🛠 Troubleshooting with Wireshark  

| Problem Type    | How to Detect in Wireshark                     | Likely Cause |
|-----------------|------------------------------------------------|--------------|
| **Packet Loss** | TCP retransmissions, missing DNS responses     | Network congestion, bad link |
| **Client Issue**| No packets leaving client, malformed requests  | Misconfigured client, firewall |
| **Server Issue**| No responses from server, RST packets seen     | Server down, overloaded, firewall rules |
| **Latency**     | High response times in DNS or TCP handshakes   | Slow routing, congestion |

---

## 📂 Example Filters Used  
```wireshark
tcp
udp
dns
tcp.analysis.retransmission
icmp
