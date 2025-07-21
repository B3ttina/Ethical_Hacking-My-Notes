## Day 02: Practical Applications and Tools

### Setting Up GitHub

1. Create an account at [github.com](https://github.com/).
2. Use the **Fork** option to duplicate existing repositories for personal experimentation.
3. To create your own repository:
   - Click on **New Repository**.
   - Fill in the project details.
   - Choose whether the repository should be public or private.

---

### Understanding VirtualBox and Kali Linux

- **VirtualBox:** Software that allows you to run virtual machines (VMs) within your host system.
- **Kali Linux:** A Debian-based operating system designed for penetration testing and ethical hacking.

#### Installation Process

- Download VirtualBox from the official site.
- Download Kali Linux in the required format (OVA or ISO file).
- In VirtualBox:
   - Either import the OVA file directly or create a new VM and attach the ISO/VDI file.
   - Allocate appropriate resources (minimum of 2GB RAM recommended).
   - Boot the virtual machine to initiate Kali Linux.

---

### Using 7zip

7zip is a tool used to extract compressed files such as `.7z` or `.zip`, commonly needed for large downloads like Kali Linux.

---

### Potential Issues During Setup

- **Hyper-V Conflicts:** Disable Hyper-V to avoid virtualization issues in VirtualBox.
- **Missing Bootable Media:** Ensure that the correct ISO/OVA file is attached.
- **Insufficient RAM Allocation:** Allocate a minimum of 2GB RAM.
- **VT-x / AMD-V Errors:** Confirm that virtualization is enabled in BIOS settings.

---

