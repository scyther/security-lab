
# 🧪 VirtualBox InfoSec Lab Setup – Documentation (Windows)

## 📘 Objective
Set up an isolated lab environment using Oracle VirtualBox to run and test various information security tools (Recon-ng, Wazuh, Wireshark, Nmap, etc.) safely without affecting your host OS.


## 📥 Step 1: Download & Install VirtualBox

1. Visit: [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
2. Download the **Windows host** version.
3. Run the installer and follow the on-screen instructions.
4. Optionally, install the **VirtualBox Extension Pack** from the same page.

---

## 📥 Step 2: Download Linux ISO

Use **Kali Linux**, **Ubuntu**, or **Parrot OS** for InfoSec purposes.

- **Kali Linux**: [https://www.kali.org/get-kali/](https://www.kali.org/get-kali/)
- **Ubuntu**: [https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)
- **Parrot OS (Security Edition)**: [https://www.parrotsec.org/download/](https://www.parrotsec.org/download/)

---

## 🧱 Step 3: Create a New Virtual Machine

1. Open VirtualBox → Click **New**.
2. Set name (e.g., `KaliLab`) → Type: Linux → Version: Debian (64-bit).
3. Assign memory (2–4 GB for light use; 6–8 GB for heavy tools).
4. Create virtual hard disk:
   - VDI → Dynamically Allocated → Size: **30–60 GB**
5. Click **Create**.

---

## 💿 Step 4: Mount ISO and Install OS

1. Select VM → **Settings → Storage**.
2. Click **Empty** under Controller: IDE → Click disk icon → **Choose a disk file** → Select ISO.
3. Go to **System** tab → Enable EFI (if using modern OS).
4. Start the VM → Follow the Linux installation process.

---

## 🌐 Step 5: Configure Network (Internal Lab)

### Option 1: NAT (Default)
- Allows VM internet access but isolates it from other VMs.

### Option 2: Host-Only Adapter (Recommended for Lab)
1. VirtualBox → **File → Host Network Manager** → Create.
2. VM Settings → Network:
   - Adapter 1: Enable → Attached to: **Host-Only Adapter**

### Option 3: Internal Network
- Use when running **multiple VMs** in a simulated LAN.

---

## 📦 Step 6: Install Guest Additions (Optional but Useful)

1. VM Running → Devices → Insert Guest Additions CD.
2. Mount and run the installer in the VM:
   ```bash
   sudo mount /dev/cdrom /mnt
   sudo /mnt/VBoxLinuxAdditions.run
   ```

---

## 🔐 Step 7: Create a Snapshot

Once OS and basic tools are installed:
1. VM → Right-click → Snapshots → Take.
2. Name it "Clean Install" or "Base Setup".

This allows rollback if your tests compromise the system.

---

## 📚 Step 8: Install Security Tools

Inside your VM, install the tools discussed earlier:
```bash
sudo apt update && sudo apt install nmap nikto wireshark openssl hashdeep
git clone https://github.com/lanmaster53/recon-ng.git
```

> Optional: Install Docker if running tools like Wazuh, ELK, etc.

---

## 🧪 Optional: Multi-VM Setup for Network Simulation

Create multiple VMs:
- `Kali`: Attacker
- `Ubuntu`: Target (web server)
- `Wazuh`: Security monitoring

Use **Internal Network** or **Host-only** mode for inter-VM communication.

Test:
```bash
ping <target-ip>
nmap <target-ip>
```

---

## 📄 Notes

- Keep snapshots before/after major changes.
- Avoid running malware on host OS.
- Use VM isolation and controlled networking.

---

## 🔗 References

- [VirtualBox Docs](https://www.virtualbox.org/manual/)
- [Ubuntu Server Guide](https://ubuntu.com/server/docs)
- [WSL vs VirtualBox Comparison](https://learn.microsoft.com/en-us/windows/wsl/compare-versions)
