# Initial Access via RDP

<img width="1450" height="639" alt="image" src="https://github.com/user-attachments/assets/f4ef0772-9132-4a83-9379-a06d56685541" />

## Questions:

- Which IP managed to breach the host via RDP (Logon Type 10)?
<img width="1699" height="719" alt="image" src="https://github.com/user-attachments/assets/366da5e4-6f79-48d8-8c49-0ce8818020f9" />

- Can you get the real Workstation Name (hostname) of the threat actor?

To get the real Workstation Name of threat actor in logs, we have to look at event with Logon Type 3, as this captures the initial NLA authentication from the external source. Logon Type 10 is a internal connection, so it's not useful.

<img width="780" height="265" alt="image" src="https://github.com/user-attachments/assets/3f128d20-f269-4e75-ae35-dfe58fa139d8" />


# Initial Access via Phishing

## LNK Attachments
Files with a .lnk file extension refers to "link files" or "desktop shortcuts". These files are often used to point to a file or folder from another location, making it convenient to access frequently used files and folders.

## Questions:
- From which URL does the malicious LNK download the next stage malware? ```http://wp16.hqywlqpa.thm:8000/cgi-bin/f```
- What is the name of the double-extension file you see there? ```best-cat.jpg.exe```

## Detecting Malicious Download
1. Sysmon Event ID 1: Web browser is launched
Image: C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe
ParentImage: C:\Windows\Explorer.EXE

2. Sysmon Event ID 11: A file (usually archive) appears in Downloads
Image: C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe
TargetFilename: C:\Users\User\Downloads\invoice.zip*

3. Sysmon Event ID 11: Optionally, the user unarchives files to some folder
Image: C:\Windows\Explorer.EXE (or C:\Program Files\7-Zip\7zG.exe)
TargetFilename: C:\Users\User\Downloads\invoice.pdf.exe

4. Sysmon Event ID 1: The user double-clicks the unarchived file
Image: C:\Users\User\Downloads\invoice.pdf.exe
ParentImage: C:\Windows\Explorer.EXE

## Questions:
- Which file did the user download via the web browser?
<img width="712" height="191" alt="image" src="https://github.com/user-attachments/assets/18cd8d0d-8c7c-4d44-9968-a90b70c683e5" />

- In which folder did the user unarchive the suspicious file? ```C:\Users\Administrator\Pictures```
<img width="1129" height="370" alt="image" src="https://github.com/user-attachments/assets/be340110-89d6-44cd-adf3-e423a515c336" />

- What is the process ID of the launched phishing malware?
<img width="524" height="151" alt="image" src="https://github.com/user-attachments/assets/b4694f4a-7997-4150-bec6-1988aa231374" />

- Finally, which malicious domain did the malware try to connect to? ```rjj.store```
<img width="746" height="294" alt="image" src="https://github.com/user-attachments/assets/073569bb-51ed-42c6-9252-bf63fefe5323" />

