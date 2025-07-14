# Day 3 — Understanding RAM, ROM, HDD, SSD (Computer Memory Systems)

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

| Feature       | Details                                                                |
|---------------|------------------------------------------------------------------------|
| What          | Non-volatile memory — data remains after power off                    |
| Use           | Stores firmware (e.g., BIOS, UEFI)                                    |
| Writable?     | Usually not writable (or very limited)                                |
| Hacker Angle  | Knowing how ROM works helps in reverse engineering firmware            |

---

## HDD (Hard Disk Drive)

| Feature       | Details                                                               |
|---------------|-----------------------------------------------------------------------|
| What          | Mechanical storage device with spinning disks                        |
| Speed         | Slower than SSD                                                       |
| Cost          | Cheaper per GB                                                        |
| Hacker Angle  | Deleted files may still exist in unallocated space — recoverable      |

### How It Works
- Read/write head moves physically across spinning platters
- Data stored magnetically in sectors and tracks
- Slower access due to mechanical delay

---

## SSD (Solid State Drive)

| Feature       | Details                                                                |
|---------------|------------------------------------------------------------------------|
| What          | Uses NAND flash memory — no moving parts                              |
| Speed         | Very fast — like a high-end USB drive                                 |
| Durability    | Silent, shock-resistant, low heat                                     |
| Hacker Angle  | SSDs often auto-wipe deleted blocks via TRIM — harder to recover data |

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

## Key Insight for Hackers

Understanding memory types helps identify where sensitive data may exist:

- RAM holds live secrets (e.g., session tokens, credentials).
- ROM locks in permanent logic (e.g., boot instructions).
- HDD/SSD contains long-term traces of activity and data.

If you know how and where data flows, you know where to look — and how to exploit or protect it.
