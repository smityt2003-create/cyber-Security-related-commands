# Cybersecurity Command Reference: Windows, macOS & Linux

A practical, beginner-friendly command-line reference for cybersecurity students, IT support learners, and junior security analysts. It covers everyday system inspection, networking, process review, logs, file integrity, and authorised security testing across the three major desktop operating-system families.

## Repository description
**Cross-platform cybersecurity command reference for Windows, macOS, and Linux. Learn system administration, networking, troubleshooting, and defensive security commands with explanations and safe lab examples.**

## What you'll learn
- Inspect IP configuration, DNS, routes, ports, and active connections.
- Review running processes, users, services, and system logs.
- Calculate file hashes and inspect file permissions.
- Use common tools such as Nmap and Wireshark in an authorised lab.
- Understand differences between PowerShell, macOS Terminal, and Linux shells.

## Repository structure
```text
cybersecurity-command-reference/
├── README.md
├── windows/
│   └── WINDOWS-COMMANDS.md
├── macos/
│   └── MACOS-COMMANDS.md
├── linux/
│   └── LINUX-COMMANDS.md
├── common-tools/
│   └── CROSS-PLATFORM-TOOLS.md
└── labs/
    └── SAFE-PRACTICE-LABS.md
```

## Getting started
1. Choose the guide for your operating system.
2. Open the appropriate terminal:
   - Windows: PowerShell (recommended) or Command Prompt.
   - macOS: Terminal.
   - Linux: your distribution's terminal.
3. Run read-only commands first and compare the output with the explanations.
4. Replace sample values such as `example.com` or `<PID>` with values from your own device or authorised lab.
5. Keep notes of the command, purpose, output, and what you learned.

## Command categories
| Category | Examples | Why it matters |
|---|---|---|
| Network discovery | `ipconfig`, `ip`, `ifconfig` | Understand local network settings |
| Connectivity | `ping`, `traceroute`, `Test-NetConnection` | Diagnose reachability |
| Ports and sessions | `netstat`, `ss`, `Get-NetTCPConnection` | Review listening ports and connections |
| Processes | `Get-Process`, `ps`, `top` | Identify running software |
| Logs | Event Viewer tools, `log`, `journalctl` | Investigate system activity |
| Integrity | `Get-FileHash`, `shasum`, `sha256sum` | Verify file integrity |

## Safety and legal use
Use scanning and testing commands only on devices, networks, and applications you own or have explicit permission to assess. Do not use this repository to access accounts, bypass security, disrupt services, or scan public systems without authorisation. Some commands require administrator/root privileges; understand the effect before running them. Prefer read-only commands while learning.

## Suggested learning path
1. Learn terminal navigation and help commands.
2. Collect your own device's IP, DNS, route, and connection information.
3. Review processes and system logs.
4. Calculate hashes for sample files and verify that the hash changes when the file changes.
5. Build a small isolated lab with virtual machines and scan only that lab.

## Contributing
Contributions are welcome. Add commands with:
- Operating system and shell.
- Exact command syntax.
- A plain-language explanation.
- A safe example.
- Any privilege requirement or warning.

## Official references
- [Microsoft Learn: Get-NetTCPConnection](https://learn.microsoft.com/en-us/powershell/module/nettcpip/get-nettcpconnection)
- [Microsoft Learn: Test-NetConnection](https://learn.microsoft.com/en-us/powershell/module/nettcpip/test-netconnection)
- [Nmap Reference Guide](https://nmap.org/docs.html)
- [Nmap on Windows](https://nmap.org/book/inst-windows.html)

---
**Disclaimer:** Educational reference only. You are responsible for complying with applicable laws, policies, and permissions.
