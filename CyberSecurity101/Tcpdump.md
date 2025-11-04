The Tcpdump tool and its libpcap library are written in C and C++ and were released for Unix-like systems in the late 1980s or early 1990s. Consequently, they are very stable and offer optimal speed.
The libpcap library is the foundation for various other networking tools today. Moreover, it was ported to MS Windows as winpcap

## Task 2: Basic

<img width="991" height="648" alt="image" src="https://github.com/user-attachments/assets/99f2012e-faeb-4dac-a2af-c68b9fe0fff9" />

## Task 3: Filtering Expressions

<img width="983" height="688" alt="image" src="https://github.com/user-attachments/assets/09d3e6bf-afdd-4b2e-86c4-eb5a20638600" />

<img width="984" height="251" alt="image" src="https://github.com/user-attachments/assets/da1173ee-22f5-4813-b13c-e055c4a028c6" />

Questions:
- How many packets in traffic.pcap use the ICMP protocol? ```26```
- What is the IP address of the host that asked for the MAC address of 192.168.124.137? ```192.168.124.148```
- What hostname (subdomain) appears in the first DNS query? ```mirrors.rockylinux.org```

## Task 4: Advanced Filtering

<img width="851" height="284" alt="image" src="https://github.com/user-attachments/assets/5efd7a77-3de1-42cc-85e6-b80ea25de7d0" />


Questions:

- How many packets have only the TCP Reset (RST) flag set? ```57```
- What is the IP address of the host that sent packets larger than 15000 bytes? ```greater 15000 ; 185.117.80.53```

## Task 5: Displaying Packets

<img width="841" height="546" alt="image" src="https://github.com/user-attachments/assets/997afabf-3ba5-40eb-a95c-10b6668575fe" />

Questions:

- What is the MAC address of the host that sent an ARP request? ```52:54:00:7c:d3:5b```




