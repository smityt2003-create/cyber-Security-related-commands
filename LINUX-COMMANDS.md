# Linux Cybersecurity Commands

**Shell:** Bash is common; commands may vary slightly by distribution. Examples suit many Debian/Ubuntu-based systems.

## 1. System information
| Command | Description |
|---|---|
| `uname -a` | Displays kernel and system information. |
| `cat /etc/os-release` | Shows Linux distribution and version details. |
| `hostnamectl` | Displays or manages host name and system metadata. |
| `whoami` | Shows the current user. |
| `id` | Displays user and group IDs. |
| `uptime` | Shows how long the system has been running and load averages. |

## 2. Network information
| Command | Description |
|---|---|
| `ip addr` | Displays IP addresses and network interfaces. |
| `ip link` | Displays network link status. |
| `ip route` | Displays the routing table. |
| `ip neigh` | Displays the neighbour cache. |
| `ping -c 4 example.com` | Sends four ICMP echo requests. |
| `traceroute example.com` | Traces network hops; may need installation. |
| `tracepath example.com` | Traces path and path-MTU information on supported systems. |
| `dig example.com` | Queries DNS records; install `dnsutils`/`bind-utils` if missing. |
| `resolvectl status` | Shows DNS configuration on systems using systemd-resolved. |

## 3. Ports and connections
| Command | Description |
|---|---|
| `ss -tulpen` | Shows listening TCP/UDP sockets and associated process details where permitted. |
| `ss -tan` | Displays TCP sockets. |
| `lsof -i -n -P` | Lists processes using network sockets; may need installation. |
| `nc -vz example.com 443` | Tests TCP connectivity to port 443. |

## 4. Processes and services
| Command | Description |
|---|---|
| `ps aux` | Lists running processes. |
| `top` | Displays live process and resource information. |
| `htop` | Interactive process viewer; may need installation. |
| `systemctl --type=service --state=running` | Lists running systemd services. |
| `systemctl status <service>` | Shows status and recent messages for a service. |
| `pgrep -a <name>` | Finds processes by name. |

## 5. Users, permissions, and files
| Command | Description |
|---|---|
| `ls -la` | Lists files, including hidden files, with permissions. |
| `getent passwd` | Lists account records from configured name services. |
| `getent group` | Lists group records. |
| `sudo -l` | Shows commands the current user may run through sudo. |
| `find <directory> -type f` | Finds regular files beneath a directory. |
| `stat <file>` | Displays file metadata and permissions. |
| `chmod` | Changes file permissions. |
| `sha256sum <file>` | Calculates a SHA-256 hash. |

## 6. Logs and security checks
| Command | Description |
|---|---|
| `journalctl -n 50` | Shows the latest 50 systemd journal entries. |
| `journalctl -p warning -b` | Shows warning-or-higher priority messages from the current boot. |
| `last` | Displays recent login sessions from the system's login records. |
| `lastb` | Displays recorded failed login attempts where supported; often requires root. |
| `sudo ufw status verbose` | Shows UFW firewall status on systems using UFW. |
| `sudo systemctl status ssh` | Checks the SSH service status where the service is named `ssh`. |

## Practice examples
```bash
# Inspect addresses and routes
ip addr
ip route

# List listening sockets
ss -tulpen

# Review recent system logs
journalctl -n 50

# Hash a sample file
sha256sum sample.txt
```

**Note:** Linux distributions differ. A command may not be installed by default, and service names differ between distributions. Use `man <command>` or `<command> --help` to read local documentation.
