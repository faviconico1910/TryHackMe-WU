# Security Log: Authentication
- Two most important Security logs: Successful Logon (4624) and Failed Logon (4625).
<img width="1531" height="299" alt="image" src="https://github.com/user-attachments/assets/5353700b-1f18-4ed9-9d00-9923172dd328" />

- Detection guide
<img width="973" height="752" alt="image" src="https://github.com/user-attachments/assets/ea863e30-7b5a-470e-87e4-3ecd86b74bce" />

## Question:
- Which IP performed a brute force of the THM-PC? ```10.10.53.248```
- Which user has been breached as a result of the attack? ``` Administrator```
- What was the Logon ID of the malicious RDP login? ```0x183C36D```


# Security Log: User Management

<img width="1466" height="460" alt="image" src="https://github.com/user-attachments/assets/0274d85b-4ddc-4275-b5a8-96b4a857a824" />

## Hunt for Backdoored Users (Expand Me)
<img width="744" height="449" alt="image" src="https://github.com/user-attachments/assets/719882d0-61eb-4125-bb68-6480da16d244" />

## Questions:
- Which user was created by the attacker soon after the RDP login? ```svc_sysrestore```
<img width="1155" height="430" alt="image" src="https://github.com/user-attachments/assets/8ddddae0-e6e5-47c6-90cc-102b118ac363" />

- Which two privileged groups was the backdoor user added to? ```Backup Operators, Remote Desktop Users```

# Sysmon: Process Monitoring
<img width="1522" height="270" alt="image" src="https://github.com/user-attachments/assets/78892fc5-5332-4098-83ac-461d2b22a0fe" />

## Analyse Process Launched
<img width="914" height="495" alt="image" src="https://github.com/user-attachments/assets/ca006301-e879-4e94-8977-f96aca38eace" />


## Questions:
- Which web browser does Sarah use to browse the web? ```Google Chrome```
- Which file did Sarah download from the browser? ```C:\Users\sarah.miller\Downloads\ckjg.exe```
<img width="534" height="184" alt="image" src="https://github.com/user-attachments/assets/25df4c17-16e5-4fd7-b48b-bb69551522dd" />

- Which URL was the file downloaded from? ```http://gettsveriff.com/bgj3/ckjg.exe```
<img width="1671" height="324" alt="image" src="https://github.com/user-attachments/assets/32ce7ee1-74c0-41cf-8639-7e0bc04900c9" />

# Sysmon: Files and Network

<img width="1529" height="268" alt="image" src="https://github.com/user-attachments/assets/57425bd9-ea2b-4807-867f-10da6da4dd13" />

## Analyst Process Activities

<img width="849" height="403" alt="image" src="https://github.com/user-attachments/assets/0803eb7f-63b2-42a4-a97d-eda368ac8d95" />

## Questions:
- Which file was created by the downloaded malware to persist on the host?
<img width="1233" height="194" alt="image" src="https://github.com/user-attachments/assets/6018a40a-b0dc-4db1-a6c3-1b6a297b6f97" />

- What is the Command & Control server malware connected to? 

Filter EventID 3: ```193.46.217.4:7777```
<img width="532" height="124" alt="image" src="https://github.com/user-attachments/assets/64a5bbf2-a8e3-402b-a7b6-df4dcc05c53b" />

- Finally, which domain does the malicious IP correspond to? ```hkfasfsafg.click```
<img width="635" height="280" alt="image" src="https://github.com/user-attachments/assets/7434ea3e-ec00-4ffb-8d43-5ed92ff42dff" />

# Powershell Logging Command

## History file
It simply records every command typed into a PowerShell window and is immediately updated when we press Enter to submit a command.
```C:\Users\<USER>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt```

## Questions:
- Which PowerShell command was executed first? ```Get-ComputerInfo```
- When did the Administrator run the first PS command?
<img width="468" height="663" alt="image" src="https://github.com/user-attachments/assets/c07b0ad9-5102-4065-8b88-688118e17c02" />

- Can you find the flag stored in the PowerShell history? ```THM{it_was_me!}```
<img width="1043" height="179" alt="image" src="https://github.com/user-attachments/assets/6a8cac77-97b0-4a04-80ae-c12df5db52ed" />
