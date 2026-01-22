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

