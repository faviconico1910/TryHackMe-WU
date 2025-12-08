# Man-in-the-Middle Attack Detection

## MITM Attack: An Overview

MITM attacks generally involve two main steps:

- Interception: The attacker inserts themselves into a communication stream, often by exploiting weaknesses in network protocols or by using techniques like ARP, DNS, or IP spoofing.
- Manipulation/Decryption: The attacker tries to access or modify the communication, decrypting encoded data or injecting harmful content, such as altered website responses or fake login forms.

## Cyber Kill Chain
<img width="1259" height="248" alt="image" src="https://github.com/user-attachments/assets/c1fd63dd-eb43-4f15-8896-526f2df2a720" />

Man-in-the-Middle is a versatile technique that adversaries primarily leverage during the Exploitation and Installation phases.

## Detecting ARP Spoofing

ARP Spoofing: In ARP spoofing, an attacker sends fake ARP replies to trick devices into associating the attacker’s MAC address with a legitimate IP, usually the default gateway. This allows the attacker to intercept, modify, or redirect traffic.

### Indicators of the Attack
- Duplicate MAC-to-IP Mappings: Multiple MAC addresses claiming the same IP address. Indicates impersonation.
- Unsolicited ARP Replies: High number of ARP replies without matching requests ("gratuitous ARP").
- Abnormal ARP Traffic Volume: A Large number of ARP packets in short intervals.
- Unusual Traffic Routing: Traffic rerouted through the attacker’s MAC.
- Gateway Redirection Patterns: Multiple destination MACs for the same gateway IP.
- ARP Probe / Reply Loops: Many ARP requests with Who has 192.168.1.x? Tell 192.168.1.y patterns

### Filters in Wireshark

- ```arp.opcode ==2 && _ws.col.info contains "192.168.10.1 is at"; arp.opcode == 2 && arp.src.proto_ipv4 == 192.168.10.1```

- ```arp.duplicate-address-detected || arp.duplicate-address-frame```

## Unmasking DNS Spoofing

### Indicators of the Attack

- Multiple DNS responses for the same query: A legitimate resolver and a forged responder reply to the same query. This is the single most reliable indicator.
- DNS response from an unexpected source: A DNS reply arrives from an IP address that does not match any configured resolver (like 8.8.8.8 or your DNS server).
- Suspiciously short TTL (Time-To-Live) values: Attackers use very low TTLs (1 - 30s) to keep poisoned entries short-lived and reassert control.
- Unsolicited DNS responses: A DNS reply appears without a corresponding DNS request from the victim.

- Filters: ```dns.flags.response == 1 && ip.src != 8.8.8.8 && dns.qry.name == "corp-login.acme-corp.local"```


## Spotting SSL Stripping in Action

### Indicators of SSL stripping

- Initial Request vs. Response: The user's initial request may be for HTTPS (port 443), but the subsequent packets immediately shift to unencrypted HTTP (port 80) for the same domain.
- Redirects/Link Rewriting: Monitoring for redirects (HTTP Status Codes 301, 302) that persistently direct an HTTPS request to an HTTP resource.
- Certificate Errors: Although the attacker usually tries to hide this, the initial TLS/SSL Handshake may fail or display a self-signed certificate if the attacker uses a more direct proxying technique.

- Filters: ```http && ip.src == 192.168.10.10 && ip.dst == 192.168.10.55```
