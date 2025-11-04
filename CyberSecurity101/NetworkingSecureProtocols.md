## Task 2: TLS
TLS is a cryptographic protocol operating at the OSI model’s transport layer.
It allows secure communication between a client and a server over an insecure network

Questions:
- What is the protocol name that TLS upgraded and built upon? ```SSL```
- Which type of certificates should not be used to confirm the authenticity of a server? ```self-signed certificate```

## Task 3: HTTPs

HTTPS stands for Hypertext Transfer Protocol Secure. It is basically HTTP over TLS. Consequently, requesting a page over HTTPS will require the following three steps (after resolving the domain name):

1) Establish a TCP three-way handshake with the target server
2) Establish a TLS session
3) Communicate using the HTTP protocol; for example, issue HTTP requests, such as GET / HTTP/1.1

Questions:
How many packets did the TLS negotiation and establishment take in the Wireshark HTTPS screenshots above? ```8```
What is the number of the packet that contain the GET /login when accessing the website over HTTPS? ```10```

## Task 4: SMTPS, POP3S, and IMAPS

<img width="1565" height="425" alt="image" src="https://github.com/user-attachments/assets/3caa39bb-d681-4388-a79a-7bf57c459c34" />

## Task 5: SSH
Questions: ```OpenSSH```

## Task 6: SFTP and FTPS
Questions:
Flag: ```THM{Protocols_secur3d}```

## Task 7: VPN (Virtual Private Network)

<img width="1168" height="766" alt="image" src="https://github.com/user-attachments/assets/5be1f9f0-11c3-491f-a9c0-47bfd2e91a91" />

## Task 8: Closing Note

Questions:
- One of the packets contains login credentials. What password did the user submit? ```THM{B8WM6P}```

