# Day 3 — Understanding RAM, ROM, HDD, SSD, GPU, Virtual Machine, Computer Specs (Computer Memory Systems)

## What I Learned

Today I explored how computers remember things — both temporarily and permanently. This is critical for hackers to understand where data lives, how it flows, and where it can be intercepted or exploited.

---

## RAM (Random Access Memory)

| Feature       | Details                                                                 |
|---------------|-------------------------------------------------------------------------|
| What          | Volatile memory — data is lost when power is off                        |
| Use           | Stores programs currently running (e.g., browser, code, session tokens) |
| Speed         | Very fast — used for immediate access                                   |
| Hacker Angle  | Sensitive data (passwords, tokens) can leak here if not cleared         |

### Physical Structure
- Built into small chips on the motherboard
- Divided into memory cells with addresses
- Stores bits using capacitors and transistors

### Types of RAM
- DRAM (Dynamic RAM): Slower, cheaper, needs refresh
- SRAM (Static RAM): Faster, expensive, used in CPU cache

---

## ROM (Read-Only Memory)

| Feature       | Details                                                                 |
|---------------|-------------------------------------------------------------------------|
| What          | Non-volatile memory — data remains after power off                      |
| Use           | Stores firmware (e.g., BIOS, UEFI)                                      |
| Writable?     | Usually not writable (or very limited)                                  |
| Hacker Angle  | Knowing how ROM works helps in reverse engineering firmware             |

---

## HDD (Hard Disk Drive)

| Feature       | Details                                                                 |
|---------------|-------------------------------------------------------------------------|
| What          | Mechanical storage device with spinning disks                           |
| Speed         | Slower than SSD                                                         |
| Cost          | Cheaper per GB                                                          |
| Hacker Angle  | Deleted files may still exist in unallocated space — recoverable        |

### How It Works
- Read/write head moves physically across spinning platters
- Data stored magnetically in sectors and tracks
- Slower access due to mechanical delay

---

## SSD (Solid State Drive)

| Feature       | Details                                                                 |
|---------------|-------------------------------------------------------------------------|
| What          | Uses NAND flash memory — no moving parts                                |
| Speed         | Very fast — like a high-end USB drive                                   |
| Durability    | Silent, shock-resistant, low heat                                       |
| Hacker Angle  | SSDs often auto-wipe deleted blocks via TRIM — harder to recover data   |

### How It Works
- Built from flash memory chips
- Data is stored in blocks and pages
- Read/write is electronic, not mechanical

---

## Summary Table

| Memory Type | Volatile | Speed     | Purpose                        |
|-------------|----------|-----------|--------------------------------|
| RAM         | Yes      | Fast      | Temporary program memory       |
| ROM         | No       | Medium    | Firmware (BIOS/UEFI) storage   |
| HDD         | No       | Slow      | Long-term file/data storage    |
| SSD         | No       | Very Fast | Fast file/program access       |

---

## GPU (Graphics Processing Unit)

A GPU is a special processor designed for graphics, parallel computation, and math-heavy tasks such as gaming, video rendering, and machine learning.

### Key Roles:
- Renders frames/images for display
- Handles 3D graphics, textures, lighting
- Accelerates machine learning (matrix operations, tensor calculations)
- Performs thousands of small tasks in parallel

### GPU vs CPU:

| Feature       | CPU                          | GPU                          |
|---------------|------------------------------|-------------------------------|
| Cores         | Few (4–16)                   | Many (1000–10,000+)           |
| Processing    | Serial (1 by 1)              | Parallel (thousands at once)  |
| Use Case      | OS, Logic, Apps              | Games, ML, Rendering          |
| Strength      | Branching logic              | Image, math, compute tasks    |

### Example GPU Spec: `NVIDIA RTX 3060, 6GB GDDR6, 3840 CUDA Cores`

| Spec              | Meaning                                           |
|-------------------|--------------------------------------------------|
| RTX 3060          | Mid-high range GPU from NVIDIA                   |
| 6GB GDDR6         | Fast graphics memory (Video RAM)                 |
| 3840 CUDA Cores   | 3840 parallel mini-processors inside the GPU     |

---

## Virtual Machine (VM)

A Virtual Machine is a software-based computer that runs inside your real computer. It has its own operating system, RAM, disk, and virtual hardware, but runs using the host system’s real hardware.

### Key Components:

| Virtual Component | Maps To (Host)               |
|-------------------|------------------------------|
| Virtual CPU       | Real CPU core                |
| Virtual RAM       | Portion of host's RAM        |
| Virtual Disk      | Host disk file (.vdi/.vmdk)  |
| Virtual NIC       | Virtual network adapter      |
| Virtual GPU       | Shared/limited access GPU    |
| Guest OS          | Linux / Windows / macOS      |

### How it Works:
1. Real OS (host) runs a hypervisor (VirtualBox, VMware).
2. You assign CPU cores, RAM, disk space to VM.
3. A guest OS is installed inside the VM.
4. It boots and behaves like a separate PC.

### Benefits:
- Isolated from host system (safe for testing)
- Great for malware analysis, OS testing, ethical hacking labs
- Host remains unaffected if VM is compromised

### Limitations:
- Performance overhead due to virtualization
- GPU access limited (unless GPU passthrough is configured)
- Cannot match native speed for resource-heavy apps

---

## Key Insight for Hackers

Understanding memory and processing components helps identify where data may exist, how it moves, and how to either exploit or secure it.  

- RAM holds live secrets like session tokens and passwords.
- ROM is where permanent boot instructions live.
- HDD/SSD store activity history and file traces.
- GPU can be leveraged for offloading processing tasks.
- Virtual Machines are ideal for isolated, secure hacking labs.

If you know how and where data flows, you know where to look — and how to exploit or protect it.
