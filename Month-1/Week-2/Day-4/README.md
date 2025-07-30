# 🌐 Day 4 – IP Addressing, Subnetting & Classes (Week 2 – Networking)

## 🧠 What I Learned (Theory)

### 🔹 1. IP Addressing (IPv4)
An **IP address** (Internet Protocol Address) is a 32-bit number that uniquely identifies a device on a network. It is written in **dotted decimal notation**, e.g., `192.168.1.1`.

Each IP address has two parts:
- **Network ID** – Identifies the network.
- **Host ID** – Identifies the device on that network.

### 🔹 2. IP Address Classes
There are 5 classes (A-E), but only A, B, and C are commonly used for host addressing.

| Class | Range                  | Default Subnet Mask | Hosts per Network | Purpose               |
|-------|------------------------|----------------------|-------------------|------------------------|
| A     | 0.0.0.0 – 127.255.255.255 | 255.0.0.0            | ~16 million       | Very large networks    |
| B     | 128.0.0.0 – 191.255.255.255 | 255.255.0.0        | ~65,000           | Medium networks        |
| C     | 192.0.0.0 – 223.255.255.255 | 255.255.255.0      | 254               | Small networks         |

### 🔹 3. Subnetting
**Subnetting** is the technique of dividing a larger network into smaller, manageable sub-networks (subnets).

- **CIDR Notation**: `/24`, `/26`, etc., represents how many bits are used for the network.
- Helps improve routing efficiency and enhances security.

#### Example:
- IP: `192.168.10.0/26`
- Subnet Mask: `255.255.255.192`
- Number of Subnets: `4`
- Hosts per Subnet: `62`

---

## 🔧 Practical Work (Hands-On)

### ✅ Task 1: Solved 10 Subnetting Problems
- Converted CIDR to subnet mask
- Found:
  - Network Address
  - Broadcast Address
  - First & Last usable IP
  - Total number of hosts
- Practiced binary-to-decimal IP conversion

📄 File: `Day4_Subnetting_Practice.pdf`

---

### ✅ Task 2: Analyzed My System's IP Configuration
- Used command-line tools:

#### On Windows:
```sh
ipconfig
