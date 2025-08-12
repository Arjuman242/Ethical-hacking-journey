# Day 1 — Wireshark Packet Capture & Analysis

## 📌 Overview
Today’s focus was on using **Wireshark** to capture, filter, and analyze network packets.  
Wireshark is an open-source network protocol analyzer that allows real-time packet inspection across OSI layers.

---

## 🛠 Tools Used
- **Wireshark** (latest version)
- **Command Prompt / Terminal** for generating network traffic

---

## 📚 Learning Objectives
1. Understand how to start and stop packet captures.
2. Apply display filters for targeted packet analysis.
3. Interpret packet details across OSI layers.
4. Practice with common networking protocols.

---

## 📂 Steps Followed

### 1. Starting a Capture
1. Launch Wireshark.
2. Select the active network interface (e.g., Wi-Fi, Ethernet).
3. Click the **blue shark fin** to start capturing packets.

---

### 2. Generating Traffic
To make packet analysis meaningful:
```bash
ping 8.8.8.8
curl example.com
