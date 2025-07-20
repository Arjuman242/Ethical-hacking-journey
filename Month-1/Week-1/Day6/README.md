# Day 6 – BIOS, UEFI & Firmware 

---

## **1. Why BIOS/UEFI Exists?**
When a computer powers on, the CPU is essentially "blank" — it has no idea where the operating system is or how to talk to hardware like storage or display.  
This is where **firmware (BIOS or UEFI)** comes in. It’s the **first code executed by the CPU** when power is turned on, responsible for:

1. **Power-On Self-Test (POST):**
   - Detecting CPU, RAM, storage, and GPU.
   - Checking for hardware faults (e.g., faulty RAM beeps).
2. **Hardware Initialization:**
   - Loads default drivers for keyboards, monitors, etc.
3. **Finding the OS Bootloader:**
   - Decides which device to boot (SSD, USB, Network).
4. **Providing a User Interface:**
   - Allows users to change boot settings, security options, and system configurations.

**Without BIOS/UEFI, your computer would remain stuck at a black screen**, unable to load any OS.

---

## **2. What is Firmware?**
- **Firmware** = The bridge between hardware and software.  
- It’s stored on a chip (ROM/Flash) and controls **how hardware behaves**.  
- Unlike regular software (apps), firmware works at the lowest level, directly controlling hardware logic.
  
### **Hardware vs Software vs Firmware:**
- **Hardware:** Physical components (CPU, RAM, SSD).
- **Software:** Programs that run on an OS (browsers, games).
- **Firmware:** Permanent code that teaches hardware how to “start and communicate” with software.

---

## **3. What is CMOS and Why It Matters?**
- BIOS/UEFI settings (boot order, system clock, enabled/disabled devices) are **stored in a chip called CMOS**.
- CMOS is battery-powered (usually a small coin cell battery on the motherboard).
  
### **Key Functions of CMOS:**
- Stores **time and date** (so your PC clock remains correct when powered off).
- Stores **custom BIOS/UEFI configurations** (e.g., if USB boot is enabled).
- **If CMOS battery dies:**  
  - Your clock resets to a default time (like 01/01/2000).  
  - BIOS/UEFI reverts to factory settings.

---

## **4. BIOS (Legacy Firmware)**
- Introduced in 1980s.
- Runs in **16-bit real mode**, limiting CPU to old instructions and small memory access.
- Uses **MBR (Master Boot Record)** to find the OS.  
  - MBR can only handle **2TB drives** and **4 partitions**.
- Limited security — malware can overwrite the boot sector (bootkit/rootkit attacks).
- No mouse/graphics support (only text interface).

---

## **5. UEFI (Modern Firmware)**
- Replaces BIOS, running in **32-bit/64-bit mode**.
- Uses **GPT (GUID Partition Table):**
  - Supports disks up to **9.4 Zettabytes** (virtually unlimited).
  - Supports up to 128 partitions.
- Provides a **graphical interface** (mouse + higher resolution).
- **Modular:** Can load drivers directly from firmware.
- **Secure Boot:** Ensures that only trusted OS bootloaders can load, preventing boot-level malware.

---

## **6. BIOS vs UEFI – Key Differences**
| Feature          | BIOS                     | UEFI                        |
|------------------|-------------------------|-----------------------------|
| Boot Mode        | MBR (2TB limit)         | GPT (9.4 ZB support)        |
| Interface        | Text-based              | GUI with mouse support      |
| CPU Mode         | 16-bit                  | 32/64-bit                   |
| Security         | No Secure Boot          | Secure Boot support         |
| Boot Speed       | Slower                  | Faster (parallel init)      |

---

## **7. Role of BIOS/UEFI in Boot Process**
### **Boot Steps:**
1. **Power On:**  
   CPU loads firmware instructions from ROM.
2. **POST (Power-On Self-Test):**  
   Verifies RAM, CPU, keyboard, GPU.
3. **Firmware Settings from CMOS:**  
   Boot order, hardware status, passwords.
4. **Locate Bootloader:**  
   - BIOS reads the first 512 bytes (MBR).
   - UEFI reads the **EFI partition** (e.g., `\EFI\BOOT\bootx64.efi`).
5. **Hand Over to OS Loader:**  
   Windows Boot Manager or Linux GRUB loads the operating system.

---

## **8. My Lenovo Ideapad UEFI Exploration**
I accessed the UEFI settings by pressing **F2 during startup**.  
Here’s what I explored:

### **Security Tab:**
- **Admin/User/HDD Passwords:** To prevent unauthorized BIOS access or disk usage.
- **AMD Platform Security Processor (PSP):** Acts like a secure co-processor for cryptography and firmware security.
- **Device Guard:** Windows-integrated feature for kernel-level protection.

### **Boot Tab:**
- **USB Boot:** Enables booting from USB devices (for OS installation or live boot).
- **PXE Boot:** Booting from a network server (used in enterprise or cloud environments).
- **Boot Priority Order:** Shows `Windows Boot Manager` and `EFI PXE Network`.

### **Configuration Tab:**
- **System Time/Date:** Controlled by CMOS battery.
- **Wireless LAN Enable/Disable:** Hardware-level control for network devices.
- **SATA Controller Mode (AHCI):** AHCI (Advanced Host Controller Interface) improves SSD performance vs older IDE mode.

---

## **9. Why BIOS/UEFI is Important for Hackers & Developers**
- **OS installation:** You can choose to boot from a USB or network.
- **Forensics/Reverse Engineering:** Secure Boot can block or allow custom OS loaders.
- **Low-level debugging:** Lets you see if hardware is detected properly before OS loads.

---

## **10. Questions I Explored**
- What happens if **Secure Boot** is disabled?  
  - Hackers can load unsigned bootloaders, potentially bypassing OS-level security.

- Why is **UEFI faster**?  
  - It initializes hardware in parallel and skips legacy delays used in BIOS.

---

## **11. Screenshots & Observations**
I captured screenshots of:
- Security settings (passwords, AMD PSP).
- Boot order (USB vs Windows Boot Manager).
- System time/date & AHCI mode.

---

## **12. Key Takeaway**
BIOS/UEFI is **not just a startup menu**, but the **foundation of how your OS even starts**.  
Understanding it means you understand the **lowest layer of your computer's security, performance, and boot sequence.**

---

## **13. Open Question for Readers**
**If UEFI Secure Boot ensures only trusted OS bootloaders can run, what could happen if a malicious actor found a vulnerability in UEFI firmware itself?**
