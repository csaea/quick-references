# Useful Commands for CTF Challenges

- **`nmap`**: 
  ```ex. nmap -sP 192.168.1.0/24  # Ping scan to find live hosts```

- **`netcat (nc)`**: 
  ```ex. nc -lvnp 1234  # Listen on port 1234```

- **`curl`**: 
  ```ex. curl -X GET http://example.com/api```

- **`wget`**:
  ```ex. wget http://example.com/file.zip```

- **`gdb`**: 
  ```ex. gdb ./vulnerable_binary```

- **`strings`**: 
  ```ex. strings secret_file.bin```

- **`file`**: 
  ```ex. file suspicious_file```

- **`grep`**: 
  ```ex. grep "flag" *.txt```

- **`binwalk`**: 
  ```ex. binwalk firmware.bin```

- **`foremost`**: 
  ```ex. foremost -i disk.img -o output_dir```

- **`hashcat`**: 
  ```ex. hashcat -m 0 -a 0 hashes.txt wordlist.txt```

- **`john`**: J
  ```ex. john --format=raw-md5 hashes.txt```

- **`sqlmap`**: 
  ```ex. sqlmap -u "http://example.com/page?id=1" --dbs```

- **`hydra`**: 
  ```ex. hydra -l admin -P passwords.txt ftp://example.com```

- **`metasploit`**: 
  ```ex. msfconsole```

- **`tcpdump`**: 
  ```ex. tcpdump -i eth0```

- **`whois`**: 
  ```ex. whois example.com```

- **`traceroute`**: 
  ```ex. traceroute example.com```
