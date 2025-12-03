# Detection: Data Exfil through DNS Tunneling
### Indicators of attack 
- Many DNS queries are sent to a single external domain, especially with very high counts compared to the baseline.
- Long subdomain labels or unusually long full query names (> 60–100 characters).
- High entropy or Base32/Base64-like patterns in the query name
- Rare record types (TXT, NULL) or many large TXT responses.
- Unusual response behavior: frequent NXDOMAIN or TCP/large UDP fragments for DNS.
- Queries at regular intervals

### Detecting through Wireshark

Filters: 
- ```dns && frame.len > 70```
- ```dns && dns.qry.name contains <REDACTED>```

### Investigating with Splunk
Search Query: 
- ```index="data_exfil" sourcetype="DNS_logs" | stats count by src_ip```
- ```index="data_exfil" sourcetype="dns_logs" | stats count by query | sort -count```

### Long query names (subdomain encoding)
- ```index="data_exfil" sourcetype="DNS_logs" | where len(query) > 30```

### Questions:
- What is the suspicious domain receiving the DNS traffic? ```tunnelcorp.net```

<img width="945" height="290" alt="image" src="https://github.com/user-attachments/assets/a127040b-e9fc-4812-bc65-b93e78a23316" />

- How many suspicious traffic/logs related to dns tunneling were observed?

<img width="938" height="751" alt="image" src="https://github.com/user-attachments/assets/1a489bc1-96c1-41d0-8ee5-ea1553541589" />

- Which local IP sent the maximum number of suspicious requests? ```192.168.1.103```

# Detection: Data Exfil through FTP
### Indicators of attack
- USER and PASS commands
- STOR (upload) and RETR (download) commands: repeated or large transfers.
- Large data connections to unusual external IPs, especially outside business hours
- Data channel openings on ephemeral ports (PASV) paired with large payloads
### Detection
Filter:
- ```ftp || ftp-data```
- Look for Credentials: ```ftp.request.command == "USER" || ftp.request.command == "PASS"```
- ```ftp contains "STOR; ftp contains "csv"```
- Identifying the traffic with a large payload size: ```ftp && frame.len > 90```

### Questions:
- How many connections were observed from the guest account? ```5```
Find string ```guest```, then select it as a filter.
<img width="830" height="203" alt="image" src="https://github.com/user-attachments/assets/786153b9-3ac6-4749-99a6-4b705c67919c" />

- Apply the filter; what is the name of the customer-related file exfiltrated from the root account? ```customer_data.xlsx```
<img width="779" height="249" alt="image" src="https://github.com/user-attachments/assets/dc42e1b0-9fd7-4afe-b182-9afd1ad5f2c8" />

- Which internal IP was found to be sending the largest payload to an external IP? ```192.168.1.105```
<img width="1271" height="143" alt="image" src="https://github.com/user-attachments/assets/22f04410-d6e3-4bef-bec1-4a850b9fb2bd" />

- What is the flag hidden inside the ftp stream transferring the CSV file to the suspicious IP? ```THM{ftp_exfil_hidden_flag}```
<img width="753" height="225" alt="image" src="https://github.com/user-attachments/assets/05ac2c2f-4acd-464f-a13d-67ccfcef736c" />

# Detection: Data Exfil via HTTP
### Indicators of Attack
- Unusually large HTTP POST requests to external/unexpected hosts.
- HTTP requests to domains with low reputation / rarely seen in baseline traffic.
- Frequent small requests (beaconing) to the same host, followed by large uploads.
- Chunked or multipart transfers where multiple requests compose a larger file.

### Analyzing Logs in Splunk
- ```index="data_exfil" sourcetype="http_logs"```
- ``` index="data_exfil" sourcetype="http_logs" method=POST | stats count avg(bytes_sent) max(bytes_sent) min(bytes_sent) by domain | sort - count```
- ```index="data_exfil" sourcetype="http_logs" method=POST bytes_sent > 600 | table _time src_ip uri domain dst_ip bytes_sent | sort - bytes_sent```
### Network Traffic Analysis
- ```http.request.method == "POST" and frame.len > 500```

### Questions:
- Which internal compromised host was used to exfiltrate this sensitive data? ```192.168.1.103```
<img width="1235" height="175" alt="image" src="https://github.com/user-attachments/assets/7d83a64a-dfda-41d8-9114-5f5e907caaaa" />

- What's the flag hidden inside the exfiltrated data? ```THM{http_raw_3xf1ltr4t10n_succ3ss}```

<img width="919" height="786" alt="image" src="https://github.com/user-attachments/assets/b09dd811-5dd2-4c34-bc53-f5e4a38c95e0" />

# Detection: Data Exfiltration via ICMP

### Indicators of attack in Wireshark
- ICMP packet volumes: a single host sending many ICMP echo requests to an external IP.
- Large frame.len or icmp.payload: pings with payloads much larger than typical (e.g., > 64 bytes). 
- ICMP type/code unusual values: e.g., unusual use of timestamp(13/14) or custom codes.
- Regular timing (periodicity): evenly spaced ICMP packets carrying similar-sized payloads.
- Fragments with reassembly: multiple ICMP fragments from the same src/dst pair.

### Filter
``` icmp.type == 8 and frame.len > 100```
### Questions:
- What is the flag found in the exfiltrated data through ICMP? ```THM{1cmp_3ch0_3xf1ltr4t10n_succ3ss}```

<img width="958" height="302" alt="image" src="https://github.com/user-attachments/assets/02b0239f-f40c-4357-8ce6-59419c9989c8" />
