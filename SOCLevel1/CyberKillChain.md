# Cyber Kill Chain Phase

## Phase 1: Reconnaissance
Reconnaissance is the research and planning phase of an attack against a system or victim. Adversaries use this phase to gather information about their target to inform their next steps. This information can include infrastructure details, employee data, business processes, and exposed technologies. Reconnaissance is often passive and undetected.

- Passive Recon: This involves having no direct interaction with the target. This may include WHOIS lookups, social media scraping, or reviewing breach data.
- Active Recon: This involves direct contact with the target with activities such as social engineering, port scanning, banner grabbing, or probing for open services.

Question:
- What is the name of the Intel Gathering Tool that is a web-based interface to the common tools and resources for open-source intelligence? ```OSINT Framework```
- What is the definition for the email gathering process during the stage of reconnaissance?```email harvesting```

## Phase 2: Weaponization

In the Weaponization phase, the attacker can adopt the following tactics:
- Create an infected Microsoft Office document containing a malicious macros or VBA (Visual Basic for Applications) scripts.
- Create a malicious payload or a very sophisticated worm, implant it on USB drives, and then distribute them in public.
- Set up Command and Control (C2) infrastructure for executing the commands on the victim's machine or deliver more payloads.
- Infect the victim's host with a backdoor, which would provide a way to access the computer system, and bypass the security mechanisms.
- Tailoring phishing templates or OAuth-consent apps to look legitimate and dupe the victim.

Question: 
- What is the term for automated scripts embedded in Microsoft Office documents that can be used to perform tasks or exploited by attackers for malicious purposes? ```Macro```

## Phase 3: Delivery

Question:
- What do you call an attack targeting a specific group by infecting their frequently visited website? ```Watering hole attack```

## Phase 4: Exploitation
Exploitation is the moment the attacker's code executes on the target, taking advantage of a known vulnerability. Signs of exploitation to look out for include:

- Unexpected process spawns.
- Registry changes or new services created.
- Suspicious command-line arguments found in system logs.

## Phase 5: Installation
Once the attacker gets access to the system, he would want to reconnect back to the system if he loses the connection to it or if he got detected and got the initial access removed. Or if the system is later patched, they will no longer have access to it. That is when the attacker needs to install a persistent backdoor. A persistent backdoor will let the attacker access the system he compromised in the past

- Installing a web shell: 
- Installing a backdoor on the victim's machine
- Creating or modifying Windows services
- Adding the entry to the "run keys" for the malicious payload in the Registry or the Startup Folder

Question:
- What technique is used to modify file time attributes to hide new or changes to existing files? ```Timestomping```

## Phase 6: Command & Control
The attacker opens up the C2 (Command and Control) channel through the malware to remotely control and manipulate the victim. 
This term is also known as C&C or C2 Beaconing as a type of malicious communication between a C&C server and malware on the infected host. The infected host will consistently communicate with the C2 server; that is also where the beaconing term came from

Question:
- What is the C2 communication where the victim makes regular DNS requests to a DNS server and domain which belong to an attacker? ```DNS Tunneling```

## Phase 7: Actions on Objectives (Exfiltration)

**FLAG**: ```THM{7HR347_1N73L_12_4w35om3}```
