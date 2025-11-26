
# Task 2: Statistics | Summary
## Statistics
This menu provides multiple statistics options ready to investigate to help users see the big picture in terms of the scope of the traffic, available protocols, endpoints and conversations, and some protocol-specific details like DHCP, DNS and HTTP/2

## Resolved Address
This option helps analysts identify IP addresses and DNS names available in the capture file by providing the list of the resolved addresses and their hostnames

<img width="1463" height="803" alt="image" src="https://github.com/user-attachments/assets/e4dd7fa5-be47-4007-b619-fc9ac67e69ab" />

## Protocol Hierarchy
This option breaks down all available protocols from the capture file and helps analysts view the protocols in a tree view based on packet counters and percentages

<img width="1463" height="648" alt="image" src="https://github.com/user-attachments/assets/dc3615e4-1f27-49b5-a64a-4501124a53f6" />

## Conversations
Conversation represents traffic between two specific endpoints. This option provides the list of the conversations in five base formats; ethernet, IPv4, IPv6, TCP and UDP.

<img width="1299" height="1200" alt="image" src="https://github.com/user-attachments/assets/080b3621-b6bd-4d50-9700-b985de88b4f2" />

## Endpoints

<img width="1463" height="784" alt="image" src="https://github.com/user-attachments/assets/01a6ee56-f113-464b-a04f-dce6713bd208" />


# Task 3: Statistics | Protocol Details

## IPv4 and IPv6
<img width="1239" height="1200" alt="image" src="https://github.com/user-attachments/assets/4d5d95ab-33b1-45ed-9afa-3e82051a64ae" />

## DNS

<img width="1463" height="879" alt="image" src="https://github.com/user-attachments/assets/e67645d5-8d0a-4713-a42d-b5a917b9aeb6" />


## HTTP
<img width="1320" height="1200" alt="image" src="https://github.com/user-attachments/assets/29f506db-87cb-4522-b2fe-f232bfcd2c07" />

# Task 4: Packet Filtering | Principles

<img width="880" height="330" alt="image" src="https://github.com/user-attachments/assets/d1ebd526-fe41-4fcd-acf8-215b87baf9c4" />

# Task 5: Pratices

- What is the number of IP packets? ```81420```
<img width="1202" height="801" alt="image" src="https://github.com/user-attachments/assets/cf77b564-e71e-4717-909d-f66cc5a739b6" />

- What is the number of packets with a "TTL value less than 10"? ```66```

<img width="1207" height="728" alt="image" src="https://github.com/user-attachments/assets/02939257-e5f4-4bba-bd9e-133272a56924" />

- What is the number of packets which uses "TCP port 4444"? ```632```

- What is the number of "HTTP GET" requests sent to port "80"? ```527```

<img width="1199" height="730" alt="image" src="https://github.com/user-attachments/assets/7289b142-4fdf-4b67-bd5f-4f17bc3364fb" />


- What is the number of type A DNS Queries? ```51```

<img width="1208" height="735" alt="image" src="https://github.com/user-attachments/assets/cd1b09f0-3f7a-4aa1-97d0-5affaee7f028" />

# Task 6: Advanced Filtering

### Filter: "contains"
<img width="1064" height="715" alt="image" src="https://github.com/user-attachments/assets/afa00115-005b-45ce-9bd0-23df54c8b47d" />


### Filter: "matches"
<img width="1074" height="718" alt="image" src="https://github.com/user-attachments/assets/1706258e-22e6-4663-bc59-5294e0e81e65" />

### Filter: "in"
<img width="1123" height="752" alt="image" src="https://github.com/user-attachments/assets/df3f03f9-131a-4814-8c7a-46dd26aa8c1c" />

### Filter: "string"
<img width="1160" height="775" alt="image" src="https://github.com/user-attachments/assets/ac3a8ffb-1deb-48ef-8068-ae5d0f6bd84d" />


### Filter: "upper"

<img width="1142" height="768" alt="image" src="https://github.com/user-attachments/assets/96c54218-7c82-45fa-a59c-f52d169f064a" />

## Question:
- Find all Microsoft IIS servers. What is the number of packets that did not originate from "port 80"? ```21```
<img width="1196" height="735" alt="image" src="https://github.com/user-attachments/assets/7e978dd6-2ac3-41e0-abcf-008661cbe1bb" />


- Find all Microsoft IIS servers. What is the number of packets that have "version 7.5"? ```71```

<img width="1200" height="726" alt="image" src="https://github.com/user-attachments/assets/97fe18ff-f4c8-4810-bfa5-8f665bd71ed2" />


- What is the total number of packets that use ports 3333, 4444 or 9999? ```2235```
<img width="1191" height="729" alt="image" src="https://github.com/user-attachments/assets/c77ea525-64b6-44f0-b16a-af6c87f67d36" />


- What is the number of packets with "even TTL numbers"? ```77289```
<img width="1192" height="811" alt="image" src="https://github.com/user-attachments/assets/c0760a7f-2473-42de-b4f8-84f4b6d811f9" />


- Change the profile to "Checksum Control". What is the number of "Bad TCP Checksum" packets? ```34185```

- Use the existing filtering button to filter the traffic. What is the number of displayed packets? ```261```
