# Task 2: Network Discovery
Defenders want to achieve the following goals:
- Inventory the organisation's assets and ensure all assets are documented.
- Ensure no unnecessary IP, port, or service is open, and whatever is running is necessary.
- Ensure vulnerabilities are patched, or at least the exploitable vulnerabilities are patched.
In short, defenders attempt to reduce the attack surface as much as possible.

### Question:
- What do attackers scan, other than, IP addresses, ports, and OS version, in order to identify vulnerabilities in a network? ```Services```

# Task 3: External vs Internal Scanning
### External Scanning Activity
<img width="856" height="783" alt="image" src="https://github.com/user-attachments/assets/a8357ec1-f13d-49f5-a501-3dd4228c444c" />

### Internal Scanning Activity

<img width="831" height="712" alt="image" src="https://github.com/user-attachments/assets/254977cd-ea3e-49b0-9e0c-c1e8058cdb8e" />

### Questions

- How many log entries are present for the internal IP performing internal scanning activity?

Command: ```grep -E "192\.168\.[0-9]+\.[0-9]+" log-session-2.csv  | wc -l```

<img width="907" height="128" alt="image" src="https://github.com/user-attachments/assets/8e86f90f-907d-4d30-9d0a-544d7f4d17e5" />

- What is the external IP address that is performing external scanning activity? ```203.0.113.25```

# Task 4: Horizontal vs Vertical Scanning (Port Scan)
### Horizontal Scanning
Scan for the same port across multiple destination IP addresses.

<img width="1047" height="590" alt="image" src="https://github.com/user-attachments/assets/54833abe-6a92-4246-9368-aa5ef7f8eb15" />

### Vertical Scanning
A single host IP address is scanned across multiple ports.

<img width="934" height="660" alt="image" src="https://github.com/user-attachments/assets/fce63c1d-f596-4338-97a7-088bd6860f5e" />


### Question:
- One of the log files contains evidence of a horizontal scan. Which IP range was scanned? Format X.X.X.X/X ```203.0.113.0/24```

**The port 8 was scanned over 203.0.113.1-254, so it's subnet is /24.**

- In the same log file, there is one IP address on which a vertical scan is performed. Which IP address is this? ```192.168.230.145```
- On one of the IP addresses, only a few ports are scanned which host common services. Which are the ports that are scanned on this IP address? Format: port1, port2, port3 in ascending order. ```80, 445, 3389```

# Task 5: The Mechanics of Scanning

### Ping Sweep
This scan is run by sending an Internet Control Message Protocol (ICMP) packet to the host. If the host is online, it will reply with an ICMP packet of its own.

### TCP SYN Scans
 The scanner sends a SYN request to the recipient. If a SYN-ACK response is received, it means that the host is online and the port on which the SYN connection was sent is also open.

### UDP Scan
Another way to identify online hosts and open ports is by sending a (usually empty) UDP packet. If the port is closed, the host sends back an ICMP port unreachable reply.

### Question
- Which source IP performs a ping sweep attack across a whole subnet? ```192.168.230.127```
<img width="1920" height="662" alt="image" src="https://github.com/user-attachments/assets/83f10449-4c98-4a5b-a04b-2e92d49bc540" />

- The zeek.conn.conn_state value shows the connection state. Using the information provided by this value, identify the type of scan being performed by 203.0.113.25 against 192.168.230.145 ```TCP SYN Scan```
- Is there any UDP scanning attempt in the logs? ```No```
