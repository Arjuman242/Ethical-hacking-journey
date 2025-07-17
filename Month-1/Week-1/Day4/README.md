# Day 4 – Operating System Fundamentals + Shell Basics (16 July)

---

##  What is an Operating System?

An **Operating System (OS)** is a crucial software layer that acts as an **intermediary between a computer's hardware and the user or application software**. It manages the system's hardware, software resources, and provides essential services for computer programs.

 Think of it as a manager: it ensures every process, program, and hardware component works smoothly and cooperatively.

---

##  Why Does an Operating System Exist?

Without an OS:
- Each software would need to know how to talk directly to hardware (like hard drives, memory, CPU), which is **extremely complex**.
- There would be **no organized way** to manage running multiple programs at once.
- No security, no file management, no user interface — total chaos.

So the OS was created to:
- Hide the complexity of hardware
- Make system usage easy for humans and programs
- Manage all resources fairly and securely

---

##  Boot Process – How the OS Gets Loaded

1. **Power On**  
   When the system is turned on, the CPU has no idea what to do — so it looks at the BIOS/UEFI chip.

2. **BIOS/UEFI Executes**  
   It performs the **POST (Power On Self Test)** and then looks for a **bootable device** (like SSD/HDD).

3. **Bootloader Loads**  
   The bootloader (like GRUB in Linux) is a tiny program that **loads the OS kernel into memory**.

4. **Kernel Takes Over**  
   The kernel initializes the system, manages memory, starts system services, and prepares the user interface.

5. **User Shell or GUI Starts**  
   Finally, the system becomes ready for user interaction — via GUI or shell.

---

## How the OS Interacts with Hardware and User

- The **Kernel** is the **core of the OS** that directly interacts with hardware using drivers.
- The **Shell** (command-line interface) or GUI (Graphical User Interface) is the interface for the **user** to interact with the system.
- System calls act as bridges between **user commands** and **hardware operations**.

**Example:**  
Typing `cat file.txt` in the shell:
- Shell interprets your command
- Passes it to kernel via system calls
- Kernel interacts with file system & disk driver
- Returns output to shell → user sees text

---

## ⚙️ Core Functions of an Operating System

| Function               | Description                                                                 |
|------------------------|-----------------------------------------------------------------------------|
| **Process Management** | Handling processes (running programs), scheduling, multitasking             |
| **Memory Management**  | Allocating/deallocating memory to processes, tracking usage                 |
| **File System**        | Managing files, directories, read/write permissions                         |
| **Device Management**  | Coordinating communication between hardware (I/O) and software              |
| **Security**           | Authentication, access control, encryption                                  |
| **User Interface**     | CLI (Shell) or GUI to allow user interaction with the system                |

---

## 🖥️ What I Practiced – Bandit Game Levels 0–3 (OverTheWire)

**Website:** [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/)

I played **Bandit Levels 0 to 3**, a beginner-friendly Linux-based wargame to learn shell basics in a fun way.

### 🧪 What I Learned from Each Level:

- **Level 0:** Logged into the remote server using `ssh bandit0@bandit.labs.overthewire.org -p 2220`  
  → Learned about SSH login, ports, and secure shell basics

- **Level 1:** Used `cat` to read a file that contains the password for next level  
  → Learned how to read a file in shell

- **Level 2:** Encountered hidden files  
  → Used `ls -a` to list hidden files  
  → Used `cat .hidden` to read it

- **Level 3:** Learned about navigating into directories using `cd` and `ls`  
  → Found password in `inhere` directory by exploring using shell navigation

### 🔤 Basic Commands Practiced:

| Command | Description                                |
|---------|--------------------------------------------|
| `pwd`   | Shows current directory                    |
| `ls`    | Lists files and folders                    |
| `cd`    | Changes directory                          |
| `cat`   | Reads and prints content of a file         |
| `echo`  | Prints text to the terminal                |
| `ls -a` | Shows all files including hidden ones      |

---

##  Reflection: Why Operating Systems Are Critical (Blog Summary)

> **“Without an Operating System, the computer is just a silent metal box with no instructions.”**

The OS abstracts the terrifying complexity of hardware and presents us with a usable, reliable, secure computing environment. Whether it's managing memory, enabling file systems, or isolating user processes — the OS is what transforms hardware into a usable machine.

---


