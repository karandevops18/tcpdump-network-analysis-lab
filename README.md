# TCPDump Network Packet Analysis Lab

![Platform](https://img.shields.io/badge/Platform-Ubuntu%2026.04-orange)
![Tool](https://img.shields.io/badge/Tool-TCPDump-blue)
![libpcap](https://img.shields.io/badge/Library-libpcap-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Status-Completed-success)

## Project Overview

This project demonstrates how to capture, analyze, filter, and save network packets using **TCPDump** on Ubuntu Linux.

The lab covers the complete workflow from installing TCPDump to capturing live network traffic, filtering packets based on protocols and hosts, saving packet captures into PCAP files, and performing offline packet analysis.

The project was created as a hands-on cybersecurity lab to build practical packet analysis skills and understand how network traffic can be inspected during troubleshooting and security investigations.

---

## Objectives

The primary objectives of this project are:

- Understand the purpose and architecture of TCPDump.
- Learn how to capture live network packets.
- Analyze ICMP, DNS, SSH, and HTTP traffic.
- Save captured traffic into PCAP files.
- Perform offline packet analysis using saved captures.
- Learn commonly used TCPDump filters.
- Practice basic network troubleshooting using packet captures.
- Build a GitHub-ready cybersecurity project with proper documentation.

---

## Key Features

- TCPDump installation and verification
- Live packet capture
- ICMP packet analysis
- DNS packet analysis
- SSH traffic capture
- HTTP traffic capture
- Save packets into PCAP files
- Offline packet analysis
- TCPDump filtering techniques
- Real-world troubleshooting examples
- Interview-focused notes
- Complete project documentation

---

## Skills Demonstrated

- Linux
- TCPDump
- Packet Capture
- Network Traffic Analysis
- ICMP
- DNS
- SSH
- HTTP
- PCAP Analysis
- Linux Networking
- Network Troubleshooting
- Cybersecurity Documentation


---

# Lab Environment

| Component | Details |
|----------|---------|
| Operating System | Ubuntu 26.04 LTS |
| Tool | TCPDump 4.99.6 |
| Packet Capture Library | libpcap 1.10.6 |
| Shell | Bash |
| Network Interface | ens33 |
| Virtualization Platform | VMware Workstation |
| Capture Format | PCAP |
| Protocols Analyzed | ICMP, DNS, SSH, HTTP |

---

# Project Structure

```text
tcpdump-network-analysis-lab/
│
├── captures/
│   └── icmp-live.pcap
│
├── docs/
│   └── screenshots/
│       ├── P1-01-os-version.png
│       ├── P1-02-kernel-version.png
│       ├── P1-03-network-interface.png
│       ├── P2-01-tcpdump-version.png
│       ├── P3A-01-icmp-capture.png
│       ├── P3B-01-dns-capture.png
│       ├── P3C-01-ssh-capture.png
│       ├── P3D-01-http-capture.png
│       └── P4-01-save-read-pcap.png
│
├── LICENSE
└── README.md
```

---

# Lab Workflow

```text
Install TCPDump
        │
        ▼
Verify Installation
        │
        ▼
Discover Network Interfaces
        │
        ▼
Capture Live Traffic
        │
        ▼
Analyze Packets
        │
        ▼
Save Packets (.pcap)
        │
        ▼
Read PCAP Files
        │
        ▼
Apply Packet Filters
        │
        ▼
Perform Network Troubleshooting
```

---

# Prerequisites

Before starting this lab, ensure the following requirements are met:

- Ubuntu Linux installed
- Administrative (sudo) privileges
- Internet connectivity
- Basic Linux command-line knowledge
- Git (optional for version control)
- TCPDump installed (or install during this lab)

---

# Learning Outcomes

After completing this project, you will be able to:

- Install and verify TCPDump on Linux.
- Capture live network traffic from different interfaces.
- Analyze common network protocols.
- Save packet captures in PCAP format.
- Perform offline packet analysis.
- Apply TCPDump filters to isolate specific traffic.
- Understand basic packet-based troubleshooting.
- Document a complete packet analysis workflow.

---

# Installation & Verification

## Step 1 - Update Package Repository

```bash
sudo apt update
```

Updating the package repository ensures that the latest package information is available before installing TCPDump.

---

## Step 2 - Install TCPDump

```bash
sudo apt install tcpdump -y
```

This installs TCPDump along with its required dependencies.

---

## Step 3 - Verify Installation

```bash
tcpdump --version
```

Expected output:

```text
tcpdump version 4.99.6
libpcap version 1.10.6
```

**Screenshot**

![TCPDump Version](docs/screenshots/P2-01-tcpdump-version.png)

---

# Phase 1 - Environment Setup

Before capturing network traffic, it is important to understand the Linux environment where TCPDump will be used.

This phase verifies the operating system, kernel version, and available network interfaces.

---

## 1. Verify Operating System

```bash
cat /etc/os-release
```

This command displays detailed operating system information.

**Screenshot**

![Operating System](docs/screenshots/P1-01-os-version.png)

---

## 2. Verify Linux Kernel Version

```bash
uname -r
```

This command displays the currently running Linux kernel version.

The kernel manages hardware resources, networking, process scheduling, and system security.

**Screenshot**

![Kernel Version](docs/screenshots/P1-02-kernel-version.png)

---

## 3. Display Network Interfaces

```bash
ip addr
```

This command displays all available network interfaces along with their IP addresses.

During this lab, the following interfaces were observed:

- **lo** – Loopback interface used for local communication.
- **ens33** – Primary network interface connected to the virtual network.

Understanding network interfaces is essential because TCPDump captures traffic from a selected interface.

**Screenshot**

![Network Interfaces](docs/screenshots/P1-03-network-interface.png)

---

# Phase 1 Summary

In this phase, the lab environment was verified successfully.

The following tasks were completed:

- Verified Ubuntu operating system.
- Verified Linux kernel version.
- Identified available network interfaces.
- Confirmed the interface that will be used for packet capture.