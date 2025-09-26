# Linux Permission Management  

Linux systems use a permission model to control access to files and directories. These permissions act like **keys**, deciding who can read, modify, or execute a file.  

Each file or directory has:  
- **Owner (User)** – the creator or assigned owner.  
- **Group** – a collection of users with shared permissions.  
- **Others** – everyone else.  

---

## 🔑 Types of Permissions  

| Symbol | Meaning | Applies To |
|--------|----------|------------|
| **r**  | Read     | View file contents / list directory contents |
| **w**  | Write    | Modify file / create, delete, rename inside directory |
| **x**  | Execute  | Run file / traverse into directory |

---

## 📂 Directory Permissions  

- **Read (`r`)** → View list of files.  
- **Write (`w`)** → Create, delete, or rename files inside.  
- **Execute (`x`)** → Traverse (enter) the directory.  

👉 Without **execute (`x`)** permission, you cannot move inside a directory, even if you can see its contents.  

Example:  

```bash
cry0l1t3@htb[/htb]$ ls -al mydirectory/
ls: cannot access 'mydirectory/script.sh': Permission denied
ls: cannot access 'mydirectory/..': Permission denied
ls: cannot access 'mydirectory/subdirectory': Permission denied

# 📜 File Permissions Representation  

### Command  

### Breakdown  
- **File Type**: `-` (file), `d` (directory), `l` (link)  
- **Owner Permissions**: `rwx` (read, write, execute)  
- **Group Permissions**: `rw-` (read, write)  
- **Other Permissions**: `r--` (read only)  

---

# ⚙️ Changing Permissions  

### Using `chmod` with symbolic notation  

### Using `chmod` with octal notation  

| Octal | Binary | Permission |
|-------|--------|------------|
| 7     | 111    | rwx |
| 6     | 110    | rw- |
| 5     | 101    | r-x |
| 4     | 100    | r-- |



# 🛡️ Special Permissions  

### 1. SUID (Set User ID)  
- Represented as `s` instead of `x`.  
- File runs with **owner’s privileges**, not the user’s.  
- Example use: programs needing elevated rights.  
- ⚠️ Security risk if applied carelessly.  

### 2. SGID (Set Group ID)  
- Similar to SUID, but runs with **group privileges**.  

### 3. Sticky Bit  
- Represented as `t` or `T` at the end of directory permissions.  
- Prevents users from deleting or renaming others’ files in shared directories.  

**Examples:**  

---

# 🚀 Summary  

- **r (read)** → View contents  
- **w (write)** → Modify contents  
- **x (execute)** → Run file / enter directory  
- **SUID/SGID** → Run as owner/group  
- **Sticky bit** → Restrict deletion in shared dirs  

Linux permission management ensures **security, collaboration, and controlled access** across files and directories.  


