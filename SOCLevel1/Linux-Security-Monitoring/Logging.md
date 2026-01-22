# Working With Text Logs
## Questions
- Which time server domain did the VM contact to sync its time? ```ntp.ubuntu.com```
<img width="1667" height="161" alt="image" src="https://github.com/user-attachments/assets/26c4f303-574b-4cc5-b8cd-5601aefe518d" />

- What is the kernel message from Yama in /var/log/syslog?
<img width="961" height="151" alt="image" src="https://github.com/user-attachments/assets/734b17da-cab6-4abf-8212-04a911a5a345" />


# Authentication Logs

```
cat /var/log/auth.log | grep -E 'session opened|session closed'
cat /var/log/auth.log | grep -E 'session opened|session closed'
cat /var/log/auth.log | grep "sshd" | grep -E 'Accepted|Failed'
cat /var/log/auth.log | grep -E '(passwd|useradd|usermod|userdel)\['
root@thm-vm:~$ cat /var/log/auth.log | grep -E 'COMMAND='
```

## Questions
- Which IP address failed to log in on multiple users via SSH? ```10.14.94.82```
- Which user was created and added to the "sudo" group? ```xerxes```

# Common Linux Logs
```
/var/log/kern.log: Kernel messages and errors, useful for more advanced investigations
/var/log/syslog (or /var/log/messages): A consolidated stream of various Linux events
/var/log/dpkg.log (or /var/log/apt): Package manager logs on Debian-based systems
/var/log/dnf.log (or /var/log/yum.log): Package manager logs on RHEL-based systems

```

## Bash History
By default, commands are first stored in memory during your session, and then written to the per-user ~/.bash_history file when log out.

```cat /home/ubuntu/.bash_history```

<img width="1535" height="375" alt="image" src="https://github.com/user-attachments/assets/3e3826af-3595-4c30-ab10-089bae2dcb54" />

## Questions
- which version of unzip was installed on the system?

<img width="901" height="258" alt="image" src="https://github.com/user-attachments/assets/b11914ee-f002-4dfd-b844-d9e7ceb376e9" />

- What is the flag you see in one of the users' bash history?

<img width="646" height="431" alt="image" src="https://github.com/user-attachments/assets/295ab7aa-8b5f-49e7-9756-ea722a5e2ee8" />


# Runtime Monitoring

## Using Auditd Example
<img width="1532" height="264" alt="image" src="https://github.com/user-attachments/assets/79e283b8-c075-4ece-9cae-55c3e85b6b01" />

The PROCTITLE shows the process command line, CWD reports the current working directory, and the remaining two lines show the system call details, like:

- pid=3888, ppid=3752: Process ID and Parent Process ID. Helpful in linking events and building a process tree
- auid=ubuntu: Audit user. The account originally used to log in, whether locally (keyboard) or remotely (SSH)
- uid=root: The user who ran the command. The field can differ from auid if you switched users with sudo or su
- tty=pts1: Session identifier. Helps distinguish events when multiple people work on the same Linux server
- exe=/usr/bin/wget: Absolute path to the executed binary, often used to build SOC detection rules
- key=proc_wget: Optional tag specified by engineers in auditd rules that is useful to filter the events

### File events

<img width="1567" height="367" alt="image" src="https://github.com/user-attachments/assets/154378fe-0107-4792-a14d-0e3eb4affbdf" />

## Questions
- When was the secret.thm file opened for the first time? (MM/DD/YY HH:MM:SS)
Note: Access to this file is logged with the "file_thmsecret" key.


<img width="1895" height="143" alt="image" src="https://github.com/user-attachments/assets/1878125e-8687-40b0-9689-4070004407d4" />

- What is the original file name downloaded from GitHub via wget?
Note: Wget process creation is logged with the "proc_wget" key.
```naabu_2.3.5_linux_amd64.zip```


- Which network range was scanned using the downloaded tool?
Note: There is no dedicated key for this event, but it's still in auditd logs.

<img width="1885" height="233" alt="image" src="https://github.com/user-attachments/assets/be227a29-aad5-42b3-ae14-1a7bf16dad2f" />
