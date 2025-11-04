## Task 4: IP Addresses and Subnets
RFC 1918 defines the following three ranges of private IP addresses:

10.0.0.0 - 10.255.255.255 (10/8)

172.16.0.0 - 172.31.255.255 (172.16/12)

192.168.0.0 - 192.168.255.255 (192.168/16)

Questions:
- Which of the following IP addresses is not a private IP address? ```49.69.147.197```
- Which of the following IP addresses is not a valid IP address? ```192.168.305.19```

## Task 5: Encapsulation
Questions:
- On a WiFi, within what will an IP packet be encapsulated? ```Frame```
- What do you call the UDP data unit that encapsulates the application data? ```Datagram```
- What do you call the data unit that encapsulates the application data sent over TCP? ```Segment```

## Task 6: Telnet
The TELNET (Teletype Network) protocol is a network protocol for remote terminal connection. In simpler words, telnet, a TELNET client, allows you to connect to and communicate with a remote system and issue text commands.
Although initially it was used for remote administration, we can use telnet to connect to any server listening on a TCP port number.

Questions:
- Use telnet to connect to the web server on 10.10.169.97. What is the name and version of the HTTP server? ```lighttpd/1.4.63```
- Use telnet to connect to the web server on 10.10.169.97. What is the name and version of the HTTP server? ```THM{TELNET_MASTER}```
