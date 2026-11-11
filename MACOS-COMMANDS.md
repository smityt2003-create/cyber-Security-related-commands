# macOS Cybersecurity Commands

**Shell:** macOS Terminal (usually zsh). Most commands below are read-only.

## 1. System information
| Command | Description |
|---|---|
| `sw_vers` | Shows macOS product name and version. |
| `uname -a` | Displays kernel and system information. |
| `hostname` | Shows the Mac's host name. |
| `whoami` | Shows the current account name. |
| `id` | Displays user ID, group ID, and group memberships. |
| `system_profiler SPSoftwareDataType` | Displays software and operating-system details. |

## 2. Network information
| Command | Description |
|---|---|
| `ifconfig` | Displays network interfaces and addresses. |
| `ipconfig getifaddr en0` | Shows the IPv4 address for interface `en0` when that is the active interface. |
| `networksetup -listallhardwareports` | Maps network hardware ports to device names. |
| `netstat -rn` | Displays the routing table. |
| `arp -a` | Displays the neighbour/ARP cache. |
| `ping -c 4 example.com` | Sends four ICMP echo requests. |
| `traceroute example.com` | Traces the route to a destination. |
| `dig example.com` | Queries DNS records. |
| `scutil --dns` | Displays configured DNS resolver information. |

## 3. Ports and connections
| Command | Description |
|---|---|
| `lsof -i -n -P` | Lists processes using network sockets, without name/port translation. |
| `lsof -iTCP -sTCP:LISTEN -n -P` | Lists processes listening on TCP ports. |
| `netstat -anv` | Displays network connection and listening socket information. |
| `nc -vz example.com 443` | Tests whether a TCP connection to port 443 can be established. |

## 4. Processes and services
| Command | Description |
|---|---|
| `ps aux` | Lists running processes. |
| `top` | Shows live process and resource information. |
| `pgrep -fl <name>` | Finds processes by name/pattern. |
| `launchctl list` | Lists launchd jobs visible to the current user. |
| ` Activity Monitor` | Open Activity Monitor from Applications > Utilities to inspect processes graphically. |

## 5. Users, permissions, and files
| Command | Description |
|---|---|
| `ls -la` | Lists files, including hidden files, with permissions. |
| `stat <file>` | Displays file metadata. |
| `chmod` | Changes file permissions. |
| `chown` | Changes file ownership; usually requires administrator privileges. |
| `shasum -a 256 <file>` | Calculates a SHA-256 hash. |
| `file <path>` | Identifies a file's type. |
| `xattr -l <file>` | Lists extended attributes, which may include quarantine metadata. |

## 6. Logs and security checks
| Command | Description |
|---|---|
| `log show --last 1h` | Shows unified log entries from the last hour; output can be large. |
| `log show --last 1h --predicate 'eventMessage CONTAINS[c] \"failed\"'` | Filters recent logs for messages containing “failed”. |
| `fdesetup status` | Reports FileVault status. |
| `spctl --status` | Reports whether Gatekeeper assessments are enabled. |
| `softwareupdate --list` | Checks for available software updates. |

## Practice examples
```bash
# Check OS version and current user
sw_vers
whoami

# Inspect active network sockets
lsof -i -n -P

# Show listening TCP services
lsof -iTCP -sTCP:LISTEN -n -P

# Calculate a file hash
shasum -a 256 sample.txt
```

**Note:** Interface names can differ between Macs. `en0` is common for Wi-Fi but is not guaranteed. Some log details require elevated permissions or may be privacy-restricted.
