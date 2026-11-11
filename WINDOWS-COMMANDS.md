# Windows Cybersecurity Commands

**Shells:** PowerShell and Command Prompt (CMD). PowerShell commands are labelled **PowerShell**.

## 1. System information
| Command | Description |
|---|---|
| `systeminfo` | Displays Windows version, hardware, boot time, and system details. |
| `hostname` | Shows the computer name. |
| `whoami` | Shows the current user account. |
| `whoami /all` | Shows user identity, groups, and security privileges. |
| `Get-ComputerInfo` | PowerShell: displays detailed operating-system and hardware information. |

## 2. Network information
| Command | Description |
|---|---|
| `ipconfig` | Shows IP address and basic adapter configuration. |
| `ipconfig /all` | Shows detailed IP, MAC, DHCP, and DNS information. |
| `ipconfig /displaydns` | Displays the local DNS resolver cache. |
| `ipconfig /flushdns` | Clears the DNS cache; useful for troubleshooting stale DNS results. |
| `ping example.com` | Tests basic reachability using ICMP where permitted. |
| `tracert example.com` | Shows the network hops towards a destination. |
| `nslookup example.com` | Queries DNS records using the configured DNS resolver. |
| `arp -a` | Displays the local IPv4-to-MAC neighbour cache. |
| `route print` | Displays the IPv4 and IPv6 routing tables. |

## 3. Ports and connections
| Command | Description |
|---|---|
| `netstat -ano` | Lists connections/listening ports with numeric addresses and process IDs. |
| `netstat -abno` | Adds executable names; may require an elevated terminal. |
| `Get-NetTCPConnection` | PowerShell: displays TCP connection details. |
| `Get-NetTCPConnection -State Listen` | PowerShell: displays TCP ports in the listening state. |
| `Get-NetTCPConnection -State Established` | PowerShell: displays established TCP connections. |
| `Get-NetUDPEndpoint` | PowerShell: lists UDP endpoints. |
| `Test-NetConnection example.com -Port 443` | Tests TCP connectivity to port 443. |

## 4. Processes and services
| Command | Description |
|---|---|
| `tasklist` | Lists running processes. |
| `tasklist /svc` | Shows services hosted by each process. |
| `Get-Process` | PowerShell: lists running processes. |
| `Get-Service` | PowerShell: lists Windows services and their status. |
| `Get-Process -Id <PID>` | PowerShell: inspects a process by its process ID. |
| `Stop-Process -Id <PID>` | PowerShell: stops a process. Use only when you understand its role. |

## 5. Users, permissions, and files
| Command | Description |
|---|---|
| `net user` | Lists local user accounts. |
| `net localgroup` | Lists local groups. |
| `icacls <path>` | Displays or modifies file and folder permissions. |
| `Get-FileHash <path> -Algorithm SHA256` | Calculates a SHA-256 file hash. |
| `Get-ChildItem -Force` | Lists files, including hidden items. |
| `Get-AuthenticodeSignature <path>` | Checks the Authenticode signature status of a file. |

## 6. Logs and security status
| Command | Description |
|---|---|
| `wevtutil el` | Lists available Windows Event Log channels. |
| `Get-WinEvent -LogName Security -MaxEvents 20` | PowerShell: reads recent Security log events; access may be restricted. |
| `Get-MpComputerStatus` | PowerShell: displays Microsoft Defender Antivirus status when available. |
| `Get-MpThreatDetection` | PowerShell: displays Defender threat detections when available. |
| `Get-HotFix` | PowerShell: lists installed Windows updates/hotfixes. |

## Practice examples
```powershell
# Review your own network configuration
Get-NetIPConfiguration

# Find listening TCP ports
Get-NetTCPConnection -State Listen

# List the processes currently running
Get-Process | Sort-Object CPU -Descending | Select-Object -First 10

# Calculate a file's SHA-256 hash
Get-FileHash .\\sample.txt -Algorithm SHA256
```

**Note:** Run PowerShell as Administrator only when a task genuinely needs elevated access. Avoid changing firewall, account, or network settings on a device you do not administer.
