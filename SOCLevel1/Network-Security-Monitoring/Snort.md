# Main Components of Snort
- Packet Decoder - Packet collector component of Snort. It collects and prepares the packets for pre-processing. 
- Pre-processors - A component that arranges and modifies the packets for the detection engine.
- Detection Engine - The primary component that processes, dissects, and analyzes the packets by applying the rules. 
- Logging and Alerting - Log and alert generation component.
- Outputs and Plugins - Output integration modules (i.e., alerts to syslog/mysql) and additional plugins (rule management detection plugins) support is done with this component. 

# Rules 

There are three types of rules available for Snort, which are explained below:

- Community Rules - Free ruleset under the GPLv2. Publicly accessible, no need for registration.
- Registered Rules - Free ruleset (requires registration). This ruleset contains subscriber rules with 30 30-day delay.
- Subscriber Rules (Paid) - Paid ruleset (requires subscription). This ruleset is the main ruleset and is updated twice a week (Tuesdays and Thursdays).

# Operation Mode 1: Sniffer

<img width="850" height="506" alt="image" src="https://github.com/user-attachments/assets/1dd18e4a-1c36-428d-ba4b-eeeb2416b824" />


# Operation Mode 2: Packet Logger

<img width="826" height="539" alt="image" src="https://github.com/user-attachments/assets/18ecc35d-bf9d-4cdb-9514-a63fdc7296c3" />


# Operation Mod 3: IDS/IPS

<img width="1341" height="780" alt="image" src="https://github.com/user-attachments/assets/883c9c4b-fc9d-4be3-aa05-0db04dabe429" />

```sudo snort -c /etc/snort/snort.conf -A full -l .```

# Operation Mod 4: 

# Snort Rules

<img width="1140" height="222" alt="image" src="https://github.com/user-attachments/assets/64fd40c7-88c4-4d87-901b-ee547d684cb4" />

There are three main rule options in Snort.

- General Rule Options - Fundamental rule options for Snort.

<img width="1550" height="700" alt="image" src="https://github.com/user-attachments/assets/a7dda678-8a4c-4022-aff1-dc042cceb61b" />

- Payload Rule Options - Rule options that help to investigate the payload data. These options are helpful to detect specific payload patterns.

<img width="1521" height="660" alt="image" src="https://github.com/user-attachments/assets/d850d0eb-8ac4-4be5-b158-e196d2b9c3f5" />


- Non-Payload Rule Options - Rule options that focus on non-payload data. These options will help create specific patterns and identify network issues.

<img width="1152" height="659" alt="image" src="https://github.com/user-attachments/assets/ac411eda-87d4-4e5c-b3e2-327e8a9047a4" />
