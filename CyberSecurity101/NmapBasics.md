Nmap is an open-source network scanner that was first published in 1997. It is a powerful and flexible network scanner that can be adapted to various scenarios and setups.
## Task 2: Host Discovery: Who Is Online

Questions:
- What is the last IP address that will be scanned when your scan target is 192.168.0.1/27?

## Task 3:
Connect Scan: ```-sT```

SYN Scan (Stealth): ```-sS```

UDP Scan: ```-sU```

```-F``` is for Fast mode, which scans the 100 most common ports 

```-p[range]```: specify a range of ports to scan

```-p-```: scan all the ports

Questions:
- How many TCP ports are open on the target system at 10.10.75.227? ```6```
- Find the listening web server on 10.10.75.227 and access it with your browser. What is the flag that appears on its main page? ```THM{SECRET_PAGE_38B9P6}```

## Task 4: Version Detection: Extract More Information

<img width="788" height="386" alt="image" src="https://github.com/user-attachments/assets/f176ff5a-0c9e-4f18-91a0-bd981f207a64" />
Questions:
- What is the name and detected version of the web server running on 10.10.75.227? ```lighttpd 1.4.74```

## Task 5: Timing

<img width="810" height="515" alt="image" src="https://github.com/user-attachments/assets/15765612-1c44-4667-888d-3d895d196f49" />

Questions:
- What is the non-numeric equivalent of -T4? ```-T aggressive```

## Task 6: Output: Controlling what you see

Questions:
- What option must you add to your nmap command to enable debugging? ```-d```

## Task 6: Conclusion
Questions:
- What kind of scan will Nmap use if you run nmap 10.10.75.227 with local user privileges? ```Connect Scan```

