# Safe Cybersecurity Practice Labs

Use your own computer or an isolated virtual network. These exercises are designed to be read-only or low impact.

## Lab 1: Build a device profile
Run the system-information and network-information commands for your OS. Record:
- OS version and hostname.
- Local IP address and default gateway.
- DNS resolver(s).
- Network interface name.

**Goal:** Understand the baseline configuration of your own device.

## Lab 2: Review listening ports
Run the appropriate command:
- Windows PowerShell: `Get-NetTCPConnection -State Listen`
- macOS: `lsof -iTCP -sTCP:LISTEN -n -P`
- Linux: `ss -tulpen`

For each listening port, identify the owning process where possible. Do not stop services just because you do not recognise them; research first.

## Lab 3: Verify file integrity
1. Create a text file named `integrity-test.txt`.
2. Calculate its SHA-256 hash using the command for your OS.
3. Add one character to the file.
4. Calculate the hash again.
5. Compare the results.

**Goal:** See how a small content change produces a different cryptographic hash.

## Lab 4: DNS and connectivity
Run `nslookup example.com` or `dig example.com`, then run `ping` to the same domain. Note that DNS resolution can succeed even when ICMP ping is blocked.

## Lab 5: Authorised Nmap scan
Only in a lab you own/control:
1. Identify the IP address of a lab VM.
2. Confirm you have permission to test it.
3. Run `nmap -sV <lab-vm-ip>`.
4. Record open ports and detected services.
5. Explain why each exposed service is needed.

## Lab report template
| Field | Notes |
|---|---|
| Date and time | |
| Operating system | |
| Lab objective | |
| Commands used | |
| Observed output | |
| What I learned | |
| Safety/permission confirmation | |
