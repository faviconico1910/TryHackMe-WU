<img width="1162" height="86" alt="image" src="https://github.com/user-attachments/assets/fc0483e4-3dd3-4bc7-9649-45c73e321739" /># Overview
System Monitor (Sysmon) is a Windows system service and device driver that, once installed on a system, remains resident across system reboots to monitor and log system activity to the Windows event log. It provides detailed information about process creations, network connections, and changes to file creation time. By collecting the events it generates using Windows Event Collection or SIEM agents and subsequently analyzing them, you can identify malicious or anomalous activity and understand how intruders and malware operate on your network.

# Sysmon Config Overview

 Sysmon includes 29 different types of Event IDs, all of which can be used within the config to specify how the events should be handled and analyzed. 
 Some of most important event IDs:
 - Event ID 1: Process Creation
 - Event ID 3: Network Connection
 - Event ID 7: Image Loaded
 - Event ID 8: CreateRemoteThread
 - Event ID 11: File Created
 - Event ID 12 / 13 / 14: Registry Event
 - Event ID 15: FileCreateStreamHash

# Malicious Activity Overview

```Get-WinEvent -Path <Path to Log> -FilterXPath '*/System/EventID=3 and */EventData/Data[@Name="DestinationPort"] and */EventData/Data=4444```

Questions:
- How many event ID 3 events are in C:\Users\THM-Analyst\Desktop\Scenarios\Practice\Filtering.evtx? ```73591```

<img width="1465" height="99" alt="image" src="https://github.com/user-attachments/assets/c04cc27b-5421-4589-8f0a-1e580002423e" />

- What is the UTC time of the first network event in the same logfile?

<img width="1920" height="764" alt="image" src="https://github.com/user-attachments/assets/5cb01a37-f07b-4047-a648-704b1e687315" />


# Detecting Mimikatz 
- Detecting File Creation: looking for files created with the name Mimikatz.
- Detecting LSASS Behavior with PowerShell:
```Get-WinEvent -Path <Path to Log> -FilterXPath '*/System/EventID=10 and */EventData/Data[@Name="TargetImage"] and */EventData/Data="C:\Windows\system32\lsass.exe"'```

# ﻿Hunting Malware
- Hunting Rats and C2 Servers
- Hunting for Common Back Connect Ports with PowerShell

# Hunting Persistence

# Detecting Evasion Techniques

# Pratical Investigations

- What is the full registry key of the USB device calling svchost.exe in Investigation 1? 
<img width="1320" height="672" alt="image" src="https://github.com/user-attachments/assets/f233a349-7ce0-418c-9ea8-d8c787168d8e" />

- What is the device name when being called by RawAccessRead in Investigation 1?

<img width="1611" height="236" alt="image" src="https://github.com/user-attachments/assets/44f6de96-de26-44a1-b737-d562339d545b" />


- What is the first exe the process executes in Investigation 1?

<img width="1466" height="533" alt="image" src="https://github.com/user-attachments/assets/946c028e-9955-4998-837b-20960b2f29f8" />

- What is the full path of the payload in Investigation 2?
<img width="1271" height="440" alt="image" src="https://github.com/user-attachments/assets/38b03abd-3fd3-4211-a13f-c2c0770d7301" />

- What is the full path of the file the payload masked itself as in Investigation 2?

<img width="891" height="118" alt="image" src="https://github.com/user-attachments/assets/1f32f2ab-f4ca-4b18-9aec-22ccecd1a593" />

- What signed binary executed the payload in Investigation 2?

<img width="768" height="186" alt="image" src="https://github.com/user-attachments/assets/a879eb45-2922-4e12-8a2d-d2f99060c4d8" />

- What is the IP of the adversary in Investigation 2?
<img width="764" height="556" alt="image" src="https://github.com/user-attachments/assets/5938ec82-61ce-44c1-97b0-3d1185d74405" />

- What back connect port is used in Investigation 2?
<img width="763" height="542" alt="image" src="https://github.com/user-attachments/assets/093b2df2-23d8-4ac6-bbde-437d1a285af6" />

- What is the IP of the suspected adversary in Investigation 3.1?
<img width="1292" height="483" alt="image" src="https://github.com/user-attachments/assets/9aab672c-5435-45f5-989a-7d54ced3a6a1" />

- What is the hostname of the affected endpoint in Investigation 3.1?
<img width="1237" height="381" alt="image" src="https://github.com/user-attachments/assets/1f871e7a-3f71-4448-bca2-995b6ddc2833" />

- What is the hostname of the C2 server connecting to the endpoint in Investigation 3.1? ```empirec2```
- Where in the registry was the payload stored in Investigation 3.1?
<img width="1318" height="499" alt="image" src="https://github.com/user-attachments/assets/68d4a79e-a7bc-483e-b089-cc7bd87297a8" />

- What PowerShell launch code was used to launch the payload in Investigation 3.1?

