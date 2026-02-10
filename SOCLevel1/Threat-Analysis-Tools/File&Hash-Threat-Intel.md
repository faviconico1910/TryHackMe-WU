# Filenames and Paths
## Filepath Analysis
```
C:\ (System drive) can be a common target for persistence mechanisms.
C:\Users\Public profile can enable cross-user access of detonated adversary tools.
C:\Users\Public\Public Downloads provides a high-traffic directory that would often evade strict monitoring.
```
## Filename Heuristic Indicators

```
Double extensions - An example of this would be invoice.pdf.exe, which leverages default Windows settings that hide file extensions.

System binary impersonation - A filename such as scvhost.exe abuses the user's familiarity with core system processes. Defenders should include legitimate locations for system processes in an allowlist, rather than standalone filenames.

High-entropy Strings – A filename such as jh8F21.exe suggests automated packing or polymorphic generation, which is commonly used in a high-churn phishing operation.

Masquerading - Filenames such as backup-2300.exe can blend with routine files, thus leveraging on reduced suspicion. Another example is a single character substitution, which can bypass detection while looking visually legitimate to an unsuspecting employee.
```

# File Hash Lookup
## Questions:
- What is the SHA256 hash of the file bl0gger?
<img width="1071" height="135" alt="image" src="https://github.com/user-attachments/assets/d9fab895-a4d9-48e3-9c5e-17353132b222" />

- On VirusTotal, what is the threat label used to identify the malicious file? ```trojan.graftor/blackmoon```
- When was the file first submitted for analysis? ```2025-05-15 12:03:49```
- According to MalwareBazaar, which vendor classified the Morse-Code-Analyzer file as non-malicious?

<img width="1584" height="279" alt="image" src="https://github.com/user-attachments/assets/a4be1157-0903-4e1e-82e0-c4a95cb1088d" />

- On VirusTotal, what MITRE technique has been flagged for persistence and privilege escalation for the Morse-Code-Analyzer file?
<img width="746" height="323" alt="image" src="https://github.com/user-attachments/assets/e3cc7157-63fe-467b-b769-bcd868545bce" />


# Sandbox Analysis

## Questions:
- What tags are used to identify the bl0gger.exe malicious file on Hybrid Analysis?
 ```BlackMoon, Discovery, windows-server-utility```
- What was the stealth command line executed from the file? ```regsvr32 %WINDIR%\Media\ActiveX.ocx /s```
<img width="1541" height="308" alt="image" src="https://github.com/user-attachments/assets/ece183eb-7f46-4d65-bd98-ee7dfe841eb1" />
- Which other process was spawned according to the process tree?
<img width="1547" height="200" alt="image" src="https://github.com/user-attachments/assets/f723d2a8-5085-41b5-8185-54616ef0a6cd" />

