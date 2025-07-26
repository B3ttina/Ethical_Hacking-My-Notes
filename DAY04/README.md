#  Networking Basics & Threat Scenarios

---

## What is a Network?
A **network** is a collection of computers or devices that are connected to share data, resources, or services. This can include LANs (Local Area Networks), WANs (Wide Area Networks), or the internet.

---

##  What is a Subnet?
A **subnet (subnetwork)** is a smaller part of a larger network.
- Helps organize networks and improve performance.
- Devices in the same subnet can communicate directly.
- Used to apply **access control** or **segmentation** for security.

---

##  What is an IP Address?
An **IP address** is a unique identifier for a device on a network.
- Example: `192.168.1.1`
- Two versions:
  - **IPv4**: 32-bit (e.g., `192.168.0.1`)  
  - **IPv6**: 128-bit, longer addresses (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`)

---

##  What is a MAC ID?
**MAC (Media Access Control) address** is a **hardware ID** assigned to a device's network interface.
- It’s permanent and unique for each device.
- Looks like: `00:1A:2B:3C:4D:5E`

---

##  IPv4 vs IPv6

| Feature         | IPv4                     | IPv6                                  |
|----------------|--------------------------|----------------------------------------|
| Address Length | 32-bit                   | 128-bit                                |
| Format         | Decimal (e.g. 192.168.0.1) | Hexadecimal (e.g. 2001:db8::1)         |
| Address Space  | ~4.3 billion addresses   | Almost unlimited (~340 undecillion)   |
| Header         | Less complex             | More efficient, simplified             |
| Security       | Optional                 | Mandatory (IPSec)                      |
| NAT Required   | Yes                      | No (direct addressing possible)        |

---

##  TCP vs UDP

| Feature               | TCP                                       | UDP                                  |
|----------------------|-------------------------------------------|--------------------------------------|
| Full Form            | Transmission Control Protocol             | User Datagram Protocol               |
| Connection           | Connection-oriented                        | Connectionless                       |
| Reliability          | Guaranteed (ACKs, retransmission)         | Not guaranteed                       |
| Speed                | Slower due to error checking               | Faster but less reliable             |
| Use Cases            | Web, email, file transfer                  | Streaming, gaming, VoIP              |
| Header Size          | Larger (20+ bytes)                         | Smaller (8 bytes)                    |
| Ordered Delivery     | Yes                                        | No                                   |

---

##  What is Port Forwarding?
**Port forwarding** allows external devices to connect to specific devices/services inside a private network.
- Used for remote access, game servers, CCTV, etc.
- Example: Forwarding port `22` to access SSH on a local system.

---

##  What is UAC?
**User Account Control (UAC)** is a Windows security feature that prevents unauthorized changes.
- When a program requests admin access, UAC prompts you to confirm.
- Prevents malware from silently making system-level changes.

---

##  What is Active & Passive Information Gathering?

| Type      | Description                                                                 |
|-----------|-----------------------------------------------------------------------------|
| Passive   | Collecting info **without interacting** with the target (e.g., WHOIS, Google) |
| Active    | Directly interacting with the target system (e.g., ping, traceroute, Nmap)     |

---

##  Nmap – Use Cases
**Nmap** is a powerful network scanner used to:
- Discover hosts and services
- Detect OS and open ports
- Perform vulnerability scanning
- Map networks

---

##  Attack Timeline (Example Case)

1. **Attacker sends a phishing email** with a password-protected `.zip` attachment.
2. Victim receives and **opens the attachment** (AVs can’t scan password-protected files).
3. Victim knows the password and **unzips the file**.
4. File is an `.exe`, **runs it unknowingly**.
5. The malware executes and **connects back to the attacker** (reverse shell).
6. Attacker uploads **PowerShell payload** to escalate control.
7. Malware **spams UAC prompts** in a loop, seeking admin access.
8. Victim accidentally clicks **"Yes"** — system gets fully compromised.

 Lesson: Never trust unexpected files — especially `.exe`s in `.zip` attachments.

---

##  Nmap Command Breakdown

Command:

```
nmap -Pn -A -sV -O -oN --script -vv -p -sS -sT
```

###  Explanation of Flags:
| Flag       | Meaning                                                                 |
|------------|-------------------------------------------------------------------------|
| `-Pn`      | Skip host discovery (treat all hosts as online)                         |
| `-A`       | Aggressive scan: OS detection, version detection, script scan, traceroute |
| `-sV`      | Detect service versions                                                 |
| `-O`       | OS detection                                                            |
| `-oN`      | Output the result in normal (human-readable) format                     |
| `--script` | Run specific or default Nmap scripts                                    |
| `-vv`      | Very verbose output (detailed)                                          |
| `-p`       | Specify port(s) to scan (e.g., `-p 80,443`)                             |
| `-sS`      | TCP SYN (stealth) scan                                                  |
| `-sT`      | TCP connect scan                                                        |
