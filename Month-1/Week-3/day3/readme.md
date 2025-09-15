# Hack The Box: File Descriptors & Redirections Module

## Overview
This module covers the fundamentals of **File Descriptors (FDs)** and **I/O redirections** in Linux. It explains how processes interact with resources (files, sockets, pipes, devices) using FDs, and how input/output can be redirected using FDs.

---

## 1. File Descriptors (FDs)

### Definition
A **File Descriptor** is a **small integer number** that represents an open file or resource in a process.  
It is an index in the process's **File Descriptor Table**, pointing to the **Open File Table** in the kernel.

### Default FDs
| FD Number | Standard Resource | Description |
|-----------|-----------------|------------|
| 0         | stdin           | Standard Input (keyboard) |
| 1         | stdout          | Standard Output (screen) |
| 2         | stderr          | Standard Error (screen) |

### How It Works
Process FD Table --> Open File Table --> Inode Table
(0,1,2,3...) (offset, mode) (metadata, disk blocks)

- `open()` → allocates a new FD  
- `read(fd, ...)` → reads from the resource associated with FD  
- `write(fd, ...)` → writes to the resource associated with FD  
- `close(fd)` → closes FD  
- `dup()` / `dup2()` → duplicates an FD (used in redirection)

### Uses of FDs
- **Files** → reading/writing to disk  
- **Sockets** → network communication  
- **Pipes** → inter-process communication (IPC)  
- **Devices** → keyboards, screens, `/dev/null`, etc.

---

## 2. Input/Output (I/O)

### Definitions
- **Input (I)**: Data coming **into** the program  
  Example: Keyboard input, reading from a file, receiving network data  
- **Output (O)**: Data going **out of** the program  
  Example: Printing to the screen, writing to a file, sending network packets  

### Analogy
