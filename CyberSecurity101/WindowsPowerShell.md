## Task 3: PowerShell Basics
Cmdlets follow a consistent ```Verb-Noun``` naming convention.
```
Get-Command
Get-Alias
Find-Module -Name
```
Questions:
- How would you retrieve a list of commands that start with the verb Remove? ```Get-Command -Name Remove*```
- What cmdlet has its traditional counterpart echo as an alias? ```Write-Output```
- What is the command to retrieve some example usage for the cmdlet New-LocalUser? ```Get-Help New-LocalUser -examples```

## Task 4: Navigating the File System and Working with Files

Questions:
- What cmdlet can you use instead of the traditional Windows command type? ```Get-Content```
- What PowerShell command would you use to display the content of the "C:\Users" directory? ```Get-ChildItem -Path C:\Users```

## Task 5: Piping, Filtering, and Sorting Data
To filter objects based on specified conditions, returning only those that meet the criteria, we can use the Where-Object cmdlet

- How would you retrieve the items in the current directory with size greater than 100? ``` Get-ChildItem | Where-Object -Property Length -gt 100 ```

## Task 6: System and Network Information
Questions:
- Other than your current user and the default "Administrator" account, what other user is enabled on the target machine? ```p1r4t3```
- This lad has hidden his account among the others with no regard for our beloved captain! What is the motto he has so bluntly put as his account's description?
```A merry life and a short one.```
- Hidden treasure inside this pirate's home: ```THM{p34rlInAsh3ll}```

## Task 7: Real-Time System Analysis
Get-FileHash: Generate file hashes, verify file integrity and detect potential tampering

Questions:
- Hidden Tresure hash:
<details>
  <summary>🔒</summary>
  71FC5EC11C2497A32F8F08E61399687D90ABE6E204D2964DF589543A613F3E08
</details>  

- What property retrieved by default by Get-NetTCPConnection contains information about the process that has started the connection? ```OwningProcess```
- Tampered Service: ```p1r4t3-s-compass```


## Task 8: Scripting
```Invoke-Command``` is essential for executing commands on remote systems, making it fundamental for system administrators, 
security engineers and penetration testers. Invoke-Command enables efficient remote management and—combining it with scripting—automation
of tasks across multiple machines. It can also be used to execute payloads or commands on target systems during an engagement by penetration testers—or attackers alike

Questions:
- What is the syntax to execute the command Get-Service on a remote computer named "RoyalFortune"? ``` Invoke-Command -ComputerName RoyalFortune -ScriptBlock { Get-Service }```
