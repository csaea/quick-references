# **Networking Commands - Linux Quick Reference**

## Table of Contents
- [Network Utilities](#network-utilities)
- [Netcat Commands](#netcat-commands)
- [Network Troubleshooting](#network-troubleshooting)

Recommended OS: Kali Linux

---

## Network Utilities

- **`ping`**: Test connectivity to a host.  `ping <hostname or IP>`
- **`ifconfig`**: Display or configure network interfaces.  `ifconfig`
- **`netstat`**: Show network connections and statistics.  `netstat -tuln`
- **`nmap`**: Scan network for hosts and open ports.  `nmap <target>`
- **`curl`**: Transfer data using protocols (HTTP, FTP).  `curl -I http://example.com`
- **`traceroute`**: Trace packet path to a destination.  `traceroute <hostname or IP>`
- **`route`**: View or modify the routing table.  `route -n`

---

## Netcat Commands

- **Listen on port**:  `nc -lvp 1234`
- **Connect to a remote host**:  `nc <hostname or IP> 1234`
- **Banner grabbing**:  `nc <hostname or IP> 80`, then `GET / HTTP/1.1`, `Host: <hostname>`
- **Send file**:  
  **Sender**:  `nc -lvp 1234 < file.txt`  
  **Receiver**:  `nc <sender_ip> 1234 > received_file.txt`

---

## Network Troubleshooting

- **`dig`**: Query DNS.  `dig example.com`
- **`tcpdump`**: Capture network traffic.  `sudo tcpdump -i eth0`
- **`hostname`**: Show or set hostname.  `hostname`

---

*Created by MD Harrell*  
For more info, visit the [Kali Linux Docs](https://www.kali.org/docs/).
