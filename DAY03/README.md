# Cybersecurity Class Notes Day03

---

## 📁 Introduction to Git & Cloning

- **Git**: A version control system that allows developers to track changes in their code and collaborate with others.
- **git clone**: This command is used to **copy (clone) a repository from a remote server like GitHub** into your local machine.

```bash
git clone <repository-URL>
```

This creates a local copy of the repository, so you can work on it offline.

---

## 🛡️ Two Types of Malware Analysis

### 1. **Static Analysis**
- This is analyzing a file **without running it**.
- Focus is on examining file properties like:
   - File type (`.exe`, `.apk`)
   - Metadata
   - Strings inside the file
   - Code structure (using disassemblers)
- Safe method because malware doesn't actually execute.

### 2. **Dynamic (Runtime) Analysis**
- This involves **executing the file in a controlled environment** to observe its real-time behavior.
- Can reveal:
   - What files it creates or modifies
   - What network connections it tries to make
   - Changes in system performance

---

## 🏝️ Sandbox

- A **sandbox** is a **virtual, isolated environment** used to safely run suspicious files without risking the host system.
- Commonly used in dynamic analysis.
- Files like `.exe` and `.apk` are often tested in sandboxes.

---

## ⚙️ ATS Software

- ATS stands for **Advanced Threat Simulation** (or similar).
- Specialized tools used to:
   - Detect complex threats
   - Simulate attack scenarios
   - Analyze how malware behaves
- It’s part of professional-level cybersecurity toolkits.

---

## 🐧 Linux Commands for Cybersecurity

### 📂 Basic File & Directory Operations

- `ls`: Lists contents of the current directory.
- `cd`: Change from the current directory to a specified destination directory.
- `pwd`: Shows your **current location** in the directory structure.
- `mkdir`: Create a **new directory** (folder).
- `rmdir`: **Remove a directory** (must be empty).
- `cp`: **Copy files or directories** from one location to another.
- `mv`: **Move** (or rename) files or directories.
- `man`: Opens the **manual page** for any Linux command.
- `echo`: Prints a message to the terminal.
- `chmod`: Changes file permissions (who can read, write, or execute the file).
- `clear`: Clears your terminal screen.

> **Note:** Linux is **case-sensitive**.

---

### 📜 File Creation Methods

- Command used:  
```bash
touch hacker.txt
```

- Creates an **empty file** called `hacker.txt`.

- To view its details:  
```bash
ls -lh
```

Where:
- `l`: shows **long list format** (permissions, owner, date modified, etc.)
- `h`: shows **human-readable file sizes** (like 1K, 2M instead of bytes).

---

### 🔐 File Permissions Basics

In Linux, each file has permissions for:
- **Owner** (creator of the file)
- **User** (other system users)
- **Others** (public)

To modify permissions, use:
```bash
chmod [permissions] [filename]
```

Example:
```bash
chmod 755 hacker.txt
```

This sets:
- Owner: read, write, execute
- Group: read, execute
- Others: read, execute

---

## 📚 Important Linux Notes

- **Linux is case-sensitive.**  
  `File.txt` and `file.txt` are different files.

- **Using `man` is essential** to understand any Linux command in depth:
```bash
man ls
```

- Always **clear your terminal** using:
```bash
clear
```

- **Explore more commands** using manuals or online resources to build proficiency.

---

> These notes are based on in-class sessions and serve as a practical reference for cybersecurity basics.
