<img width="1919" height="743" alt="image" src="https://github.com/user-attachments/assets/73e813c1-0d7a-49f9-9e85-c660a8a79cc7" />
# Task 2: Nmap Scans

### TCP Connect Scans

```tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size > 1024```

<img width="1053" height="279" alt="image" src="https://github.com/user-attachments/assets/87f76e31-7047-42f7-862d-49a6e2846086" />

### SYN Scans

<img width="1085" height="250" alt="image" src="https://github.com/user-attachments/assets/c1f775bd-1e10-41be-b889-561b16ace8b7" />

```tcp.flags.syn==1 and tcp.flags.ack==0 and tcp.window_size <= 1024```

### UDP Scans

<img width="1081" height="201" alt="image" src="https://github.com/user-attachments/assets/e9130bb6-3b21-4953-9189-5f2003d243fa" />

CLosed port: ```icmp.type==3 and icmp.code==3```

### Questions:

- What is the total number of the "TCP Connect" scans? ```1000```

<img width="1204" height="837" alt="image" src="https://github.com/user-attachments/assets/afbd0d1a-3c34-4601-9604-ac71d1ec3fde" />

- Which scan type is used to scan the TCP port 80? ```TCP Connect```

- How many "UDP close port" messages are there? ```1083```

<img width="1198" height="719" alt="image" src="https://github.com/user-attachments/assets/22c69538-ea97-4640-973d-48dc73d3f5d7" />


- Which UDP port in the 55-70 port range is open? ```68```

# ARP Poisoning & Man In The Middle!

<img width="1527" height="502" alt="image" src="https://github.com/user-attachments/assets/fafa8d8c-06f5-4b38-aea9-66108b4522c1" />

### Possible IP Spoofing

<img width="1568" height="601" alt="image" src="https://github.com/user-attachments/assets/389d34b3-5b5d-45bf-a46b-dfd261a21be9" />

<img width="1519" height="459" alt="image" src="https://github.com/user-attachments/assets/bcff0299-2f33-4d36-bc8b-b0dee807bbf7" />

### Questions
- What is the number of ARP requests crafted by the attacker? ```284```
<img width="1919" height="743" alt="image" src="https://github.com/user-attachments/assets/64468a72-2055-4627-b94b-217ff62987ed" />


- What is the number of HTTP packets received by the attacker? ```90```
  
<img width="1911" height="733" alt="image" src="https://github.com/user-attachments/assets/b55a0680-9673-476b-926c-ad1f16970cc6" />

- What is the number of sniffed username&password entries? ```7```


- What is the password of the "Client986"? ```clientnothere!```

<img width="1911" height="150" alt="image" src="https://github.com/user-attachments/assets/227259b8-a8cb-4c2c-b52c-136609612bf2" />

- What is the comment provided by the "Client354"? ```Nice work!```
<img width="1920" height="180" alt="image" src="https://github.com/user-attachments/assets/f5850a20-2821-463f-b472-79be66ea6b2d" />
