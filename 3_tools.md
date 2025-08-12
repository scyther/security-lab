
# 🛡️ Information Security Tools

## 1. 🔍 Footprinting: Recon-ng

**Purpose**: Recon-ng is a reconnaissance framework to automate OSINT gathering.

**Documentation**: [Recon-ng GitHub](https://github.com/lanmaster53/recon-ng)

**Tutorial**: [Recon-ng Tutorial](https://hackertarget.com/recon-ng-tutorial/)

---

## 2. 🔥 Firewall: UFW (Uncomplicated Firewall)

**Purpose**: Manage firewall rules easily on Ubuntu.

**Installation**:
```bash
sudo apt install ufw
```

**Usage**:
```bash
sudo ufw enable
sudo ufw allow 22/tcp
sudo ufw status verbose
```

**Documentation**: [UFW Docs](https://help.ubuntu.com/community/UFW)  
**Tutorial**: [UFW Tutorial](https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands)

---

## 3.🦠 Antivirus Software: ClamAV

**Purpose**: Open-source antivirus for Linux systems.

**Installation**:
```bash
sudo apt install clamav clamav-daemon
```

**Usage**:
```bash
# Update database
sudo freshclam

# Scan directory
clamscan -r /path/to/scan
```

**Documentation**: [ClamAV Docs](https://docs.clamav.net/)  
**Tutorial**: [ClamAV Tutorial](https://hackertarget.com/clamav-tutorial-antivirus-linux/)

---


## 4. 🔑 Public Key Infrastructure (PKI): OpenSSL

**Purpose**: Generate and manage keys, CSRs, and certificates.

**Installation**:
```bash
sudo apt install openssl
```

**Usage**:
```bash
openssl genrsa -out private.key 2048
openssl req -new -key private.key -out request.csr
openssl req -x509 -days 365 -key private.key -in request.csr -out certificate.crt
```

**Documentation**: [OpenSSL Docs](https://www.openssl.org/docs/)  
**Tutorial**: [OpenSSL Tutorial](https://www.geeksforgeeks.org/linux-unix/practical-uses-of-openssl-command-in-linux/)

---

## 5. 🧠 Managed Detection & Response (MDR): Wazuh

**Purpose**: Open-source XDR/MDR platform.

**Installation** (Ubuntu with Docker):
```bash
sudo apt install docker.io docker-compose git
git clone https://github.com/wazuh/wazuh-docker.git
cd wazuh-docker
docker-compose up -d
```

**Access**: `https://localhost` in browser.

**Documentation**: [Wazuh Docs](https://documentation.wazuh.com/current/index.html)  
**Tutorial**: [Wazuh Installation Guide](https://www.geeksforgeeks.org/ethical-hacking/introduction-to-wazuh/)

---

## 6. 📡 Port Scanner: Nmap

**Purpose**: Scan networks and hosts for open ports/services.

**Installation**:
```bash
sudo apt install nmap
```

**Usage**:
```bash
nmap scanme.nmap.org
nmap -O scanme.nmap.org
nmap -A 192.168.1.0/24
```

**Documentation**: [Nmap Docs](https://nmap.org/)  
**Tutorial**: [Nmap Tutorial 1](https://www.freecodecamp.org/news/what-is-nmap-and-how-to-use-it-a-tutorial-for-the-greatest-scanning-tool-of-all-time/), [Nmap Tutorial 2](https://www.geeksforgeeks.org/linux-unix/top-30-basic-nmap-commands-for-beginners/)

---

## 7. 🌐 Packet Sniffer: Wireshark

**Purpose**: Capture and analyze network packets.

**Installation**:
```bash
sudo apt install wireshark
sudo usermod -aG wireshark $USER
```

**Usage**:
```bash
wireshark
```

**Documentation**: [Wireshark User Guide](https://www.wireshark.org/docs/wsug_html_chunked/)  
**Tutorial**: [Wireshark Tutorial](https://www.geeksforgeeks.org/linux-unix/how-to-install-and-use-wireshark-on-ubuntu-linux/), [Wireshark Basics](https://www.geeksforgeeks.org/computer-networks/wireshark-packet-capturing-and-analyzing/)

---

## 8. 🧰 Vulnerability Scanner: Nikto

**Purpose**: Web server vulnerability scanner.

**Installation**:
```bash
sudo apt install nikto
```

**Usage**:
```bash
nikto -h http://target.com
```

**Documentation**: [Nikto GitHub](https://github.com/sullo/nikto)  
**Tutorial**: [Nikto Tutorial](https://www.hackercoolmagazine.com/nikto-vulnerability-scanner-complete-guide/?srsltid=AfmBOorA_oWMb6VXafSSBszghjHOiO5YecOstDSye5hKewEvSobaBU60)

---

## 9. 🗃️ Hashing & File Integrity: Hashdeep

**Purpose**: Compute hashes and verify file integrity.

**Installation**:
```bash
sudo apt install hashdeep
```

**Usage**:
```bash
hashdeep -r folder/
hashdeep -r -vv -a -k hashes.txt folder/
```

**Documentation**: [Hashdeep Docs](https://github.com/jessek/hashdeep)  
**Tutorial**: [Hashdeep Tutorial](https://www.geeksforgeeks.org/ethical-hacking/hashdeep-a-digital-forensics-tool-in-kali-linux/)

---

## 📝 Tips

- Always update your system before installing tools:
```bash
sudo apt update && sudo apt upgrade -y
```
- Use VirtualBox snapshots to save clean states.
- Run tools in an isolated lab to avoid risks.
- A complete list of security tools can be found in the [Kali Linux Tools Documentation](https://www.kali.org/tools/).
