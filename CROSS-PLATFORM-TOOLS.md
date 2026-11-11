# Cross-Platform Security Tools

These tools are available on more than one operating system. Installation methods and permissions differ.

| Tool | Main use | Safe learning example |
|---|---|---|
| Nmap | Network discovery and port/service inventory | `nmap -sV <your-lab-host>` |
| Wireshark / TShark | Packet capture and protocol analysis | Capture traffic from your own lab interface |
| Git | Version control for notes, scripts, and projects | `git status` |
| OpenSSL | Inspect certificates and perform cryptographic operations | `openssl version` |
| Python | Scripting and automation | `python --version` |
| cURL | Make HTTP requests and inspect responses | `curl -I https://example.com` |

## Nmap basics
```bash
# Confirm installed version
nmap --version

# Scan only a host you own or are authorised to test
nmap -sV <authorised-lab-ip>

# Save results in normal text format
nmap -oN scan-results.txt <authorised-lab-ip>
```

`-sV` attempts service/version detection. Scans can generate network traffic and may be logged. Never scan systems without permission.

## Git basics
```bash
git init
git status
git add .
git commit -m "Add cybersecurity command notes"
```

## Useful official documentation
- Nmap: https://nmap.org/docs.html
- Wireshark: https://www.wireshark.org/docs/
- Git: https://git-scm.com/docs
- OpenSSL: https://docs.openssl.org/
- Python: https://docs.python.org/3/
