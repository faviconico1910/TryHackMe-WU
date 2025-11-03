# Task 2:
Use ``` set ``` to check Windows Path

Questions:
- What is the OS version of the Windows VM? ```10.0.20348.2655```
- What is the hostname of the Windows VM? ```WINSRV2022-CORE```
  
# Task 3

Questions:
- Which command can we use to look up the server’s physical address (MAC address)? ```ipconfig /all```
- What is the name of the service listening on port 135? ```RpcSs (Remote Procedure Call)```
- What is the name of the service listening on port 3389? ```TermService```

# Task 4
``` dir /a ``` display all hidden and system files. ```dir /s ``` displays files in the current directory and all subdirectories.
``` type ``` lists file content
- What are the file’s contents in C:\Treasure\Hunt? ```THM{CLI_POWER}```

# Task 5

- What command would you use to find the running processes related to notepad.exe? ```tasklist /FI "imagename eq notepad.exe"```
- What command can you use to kill the process with PID 1516? ``` taskkill /PID 1516 ```
