# **Week 1 Recap: Foundations of Computers & Systems**

This week was about **understanding computers from the ground up** — from hardware to operating systems, file systems, and BIOS/UEFI. Below is a complete summary of what I learned, along with deep questions and their answers.

---

## **Day 1: What is a Computer?**

### **Key Concepts**
- A computer is an electronic machine that processes data and performs tasks according to instructions.
- Major components:
  - **CPU (Central Processing Unit):** Brain of the computer.
  - **RAM (Random Access Memory):** Temporary memory for active processes.
  - **Motherboard:** Main circuit board connecting all components.
  - **Storage:** HDD (Hard Disk Drive) or SSD (Solid State Drive).
  - **I/O Devices:** Keyboard, mouse, display.

### **Deep Questions**
1. **Why is CPU called the brain of the computer?**
   - Because it performs all the calculations and logic, controlling all other components.

2. **Why do we need both RAM and Storage?**
   - RAM is fast and temporary, used while programs are running. Storage is permanent but slower.

---

## **Day 2: Binary System**

### **Key Concepts**
- All computers understand only **0 and 1 (binary)**.
- **1 byte = 8 bits.**
- Binary-to-decimal conversion and vice versa.

### **Deep Question**
- **Why do computers use binary instead of decimal?**
  - Binary is easier to represent electronically using on/off (high/low voltage).

---

## **Day 3: Memory (RAM, ROM, HDD, SSD)**

### **Key Concepts**
- **RAM:** Temporary memory, volatile.
- **ROM:** Read-only memory (stores firmware).
- **HDD:** Uses spinning disks, slower.
- **SSD:** Uses flash memory, much faster.

### **Deep Question**
- **Why are SSDs faster than HDDs?**
  - SSDs have no moving parts; data is accessed electronically, while HDDs rely on mechanical spinning.

---

## **Day 4: Operating System & Shell**

### **Key Concepts**
- **Why OS exists?**
  - Without an OS, users can't interact with hardware easily.
  - OS manages memory, runs programs, provides UI, and ensures security.

- **Kernel vs Shell:**
  - Kernel interacts directly with hardware.
  - Shell is the interface for users (CLI or GUI).

- **Basic Commands:** `ls`, `pwd`, `cd`, `cat`, `echo`.

### **Deep Questions**
1. **What would happen if OS didn’t exist?**
   - Users wouldn’t know how to communicate with hardware, no UI, no process management.

2. **How does OS interact with hardware and user?**
   - User inputs commands → Shell passes it to the OS → OS uses drivers to interact with hardware → Output is shown to user.

---

## **Day 5: File Systems (FAT32, NTFS, ext4)**

### **Key Concepts**
- **Why File Systems?**
  - To organize and manage files on storage devices.

- **FAT32:**
  - Old system, max file size = 4GB, max partition = 2TB.

- **NTFS (Windows default):**
  - Supports large files, journaling, permissions, encryption.

- **ext4 (Linux default):**
  - Supports extents (efficient storage), journaling, delayed allocation.

### **Deep Questions**
1. **Why do different OSes use different file systems?**
   - Each OS optimizes its file system for performance, security, and features.

2. **What is journaling in file systems?**
   - It logs changes before applying them, preventing corruption during crashes.

---

## **Day 6: BIOS, UEFI, Firmware**

### **Key Concepts**
- **BIOS (Basic Input Output System):**
  - First code that runs when the PC powers on.
  - Initializes hardware and loads the bootloader.

- **UEFI (Unified Extensible Firmware Interface):**
  - Modern replacement for BIOS.
  - Supports secure boot, large disks (up to 9.4 ZB with GPT), and better UI.

- **Firmware:**
  - Software stored in hardware (e.g., BIOS) that controls how the hardware operates.

### **Deep Questions**
1. **What is CMOS, and why does BIOS need a battery?**
   - CMOS stores BIOS settings like time, date, and boot order. Battery keeps data when power is off.

2. **Why transition from BIOS to UEFI?**
   - BIOS was 16-bit, slow, and limited to 2TB disks. UEFI is faster, secure, and future-ready.

3. **What is the role of BIOS/UEFI in boot process?**
   - Power On → BIOS/UEFI runs POST → Loads bootloader (e.g., Windows Boot Manager or GRUB).

---

## **Key Takeaways**
- Computers work in layers: **Hardware → Firmware → OS → User Interface.**
- Understanding these foundations is essential for hacking, troubleshooting, and building secure systems.

---

## **Questions for You**
- **If BIOS is replaced with UEFI, what new security advantages do we get?**
- **Can you think of scenarios where FAT32 is better than NTFS despite its limits?**

