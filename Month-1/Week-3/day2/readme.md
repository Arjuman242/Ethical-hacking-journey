# Linux Basics for Hackers – Day 1

## 📌 Topics Covered
1. **Intro to Linux**
   - Filesystem structure:
     - `/` (root directory)
     - `/home` (user home directories)
     - `/etc` (config files)
     - `/bin`, `/sbin`, `/usr/bin` (system commands)
     - `/var` (logs, changing files)
   - Basic Commands:
     - `pwd` → show current directory
     - `ls, ls -la` → list files
     - `cd` → change directory
     - `touch` → create file
     - `mkdir` → create directory
     - `cp`, `mv` → copy/move
     - `rm` → delete file/folder
     - `cat`, `less`, `head`, `tail` → read files
     - `whoami`, `id`, `uname -a` → system info

---

2. **Kali Linux Terminal & File Permissions**
   - Permissions format: `rwxr-xr--`
   - Commands:
     - `ls -l` → show permissions
     - `chmod` → change permissions
       - Example: `chmod 755 file.txt`
       - Example: `chmod +x script.sh`
     - `chown` → change file owner
     - `chgrp` → change file group

---

3. **OverTheWire: Bandit Practice**
   - Connected using:
     ```bash
     ssh bandit0@bandit.labs.overthewire.org -p 2220
     ```
   - Practiced commands: `cat`, `ls -a`, `file`, `strings`, `grep`, `find`
   - Completed Levels: **0 → 5**
   - Learned:
     - Hidden files (`ls -a`)
     - Reading passwords with `cat`
     - Using `file` to identify unknown files
     - Extracting text from binaries using `strings`
     - Searching with `grep` and `find`

---

4. **Book Reference**
   - *Linux Basics for Hackers* – Chapters 1 & 2
   - Practiced every command shown in the book.

---

## ✅ Today’s Takeaway
- I can navigate Linux filesystem confidently.  
- I understand file permissions (`rwx`).  
- I practiced hacking-style Linux basics using Bandit levels.  
- Next step → Bandit Levels 6–10
