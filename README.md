# 🔍 Basic Network Reconnaissance using Nmap & Wireshark

**Objective:** Understand network service exposure by scanning and analyzing open ports and traffic within a local network.

---

## 🧰 Tools Used

* **Nmap** – Port scanning and host discovery
* **Wireshark** – Packet capturing and protocol analysis

---

## 🔧 Nmap Commands: Host and Port Scanning

### 🔹 1. Scan the Local Network for Active Hosts

```bash
nmap -sn 192.168.1.0/24
```

* **Purpose**: Detects all online devices (ping scan only)
* **Use Case**: Discover hosts in your local subnet

---

### 🔹 2. Scan a Specific Host for Open Ports

```bash
nmap -sS 192.168.1.10 -oN open_ports.txt
```

* **-sS**: TCP SYN scan (stealthy and quick)
* **-oN open\_ports.txt**: Save results to a readable file

---

### 🔹 3. Fast Scan for Top 100 Common Ports Across Subnet

```bash
nmap -sS --top-ports 100 -T4 192.168.1.0/24
```

* **--top-ports 100**: Scans only the 100 most common ports
* **-T4**: Aggressive timing for faster scanning

---

### 🔹 4. Full Port Scan on a Specific Host

```bash
nmap -sS -Pn -p- 192.168.1.10
```

* **-Pn**: Skips ping check (treats host as up)
* **-p-**: Scans all 65535 TCP ports

---

## 📘 Nmap Flag Reference

| Flag              | Meaning                                      |
| ----------------- | -------------------------------------------- |
| `-sS`             | TCP SYN scan (stealthy and fast)             |
| `-Pn`             | Skip ping; assume host is online             |
| `-p-`             | Scan all ports (1–65535)                     |
| `--top-ports 100` | Scan top 100 most common ports               |
| `-T4`             | Use aggressive timing (faster scan)          |
| `-sn`             | Ping scan only (no port scan)                |
| `-oN <file>`      | Output scan results to a file in normal text |

---

## 📡 Wireshark: Packet Capture and Traffic Filtering

### 🎯 Purpose:

Capture and analyze real-time network traffic to understand communication between devices and detect service exposure.

---

### 🔎 Common Wireshark Display Filters

| Filter                    | Description                         |
| ------------------------- | ----------------------------------- |
| `http`                    | Only shows HTTP traffic             |
| `ip.addr == 192.168.1.10` | Packets involving a specific IP     |
| `tcp.port == 80`          | All packets over TCP port 80 (HTTP) |
| `icmp`                    | Ping packets (Echo Request/Reply)   |
| `dns`                     | DNS queries and responses only      |

---

## ✅ Learning Outcomes

* Understood the basics of **active reconnaissance** using Nmap
* Gained hands-on experience in **scanning local IP ranges** and identifying **open or filtered ports**
* Learned to **capture and filter packets** in Wireshark for better traffic visibility
* Built foundational skills in **network security and exposure analysis**

---
