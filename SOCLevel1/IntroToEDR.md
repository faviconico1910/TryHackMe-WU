# Introduction to EDR

## Task 1: Introduction
Endpoint Detection and Response (EDR) is a security solution designed to monitor, detect, and respond to advanced threats at the endpoint level.

## Task 2: What is an EDR?
Below are some of the EDR solutions in the market:
- CrowdStrike Falcon
- SentinelOne ActiveEDR
- Microsoft Defender for Endpoint
- OpenEDR
- Symantec EDR

## Task 3: Beyond the Antivirus
There are three main features of an EDR, which can also be referred to as the three pillars of an EDR solution.
- Visibility: It collects detailed data from the endpoints, which includes process modifications, registry modifications, file and folder modifications, user actions, and much more.
- Detection: It incorporates signature-based detections as well as behavior-based detections, such as unexpected user activities. With modern machine learning capabilities, it identifies any deviation from the baseline behavior and instantly flags it. 
It can also detect fileless malware that resides in memory. It also allows us to feed custom IOCs for threat detections.
- Response:  isolate a complete endpoint, terminate a process, or quarantine some files, connect to the host remotely and execute actions independently.

## Task 5: Telemetry
- Telemetry: different data from endpoints and being pushed to the EDR console.This detailed telemetry not only helps the EDR detect advanced threats and make better judgments on the legitimacy of the activities, but it is also very helpful for the analysts during the investigations. The analysts can understand the full chain of events, identify the root cause, and reconstruct the attack timeline.

## Task 6:
Detection:
- Behavioral Detection
- Anomaly Detection
- IOC matching
- MITRE ATT&CK Mapping
- Machine Learning Algorithms

Response: Isolate Host, Terminate Process, Quarantine, Remote Access, Artefacts Collection

Question:
- Which feature of the EDR helps you identify threats based on known malicious behaviours?  ```IOC Matching```

## Task 6
Question:
- Which tool was launched by CMD.exe to download the payload on DESKTOP-HR01? ```CURL.exe```
- What is the absolute path to the downloaded malware on the DESKTOP-HR01 machine? ```What is the absolute path to the downloaded malware on the DESKTOP-HR01 machine?```
- What is the absolute path to the suspicious syncsvc.exe on the WIN-ENG-LAPTOP03 machine? ```C:\Users\haris.khan\AppData\Local\Temp\syncsvc.exe```
- On which URL was the exfiltration attempt being made on WIN-ENG-LAPTOP03? ```https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dmp```
- What was UpdateAgent.exe labelled by Threat Intel on DESKTOP-DEV01? ```Known internal IT utility tool```
