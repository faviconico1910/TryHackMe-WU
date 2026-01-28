# Initial Access via SSH

## Questions
- When did the ubuntu user log in via SSH for the first time? ```2024-10-22```

<img width="1896" height="385" alt="image" src="https://github.com/user-attachments/assets/af22b4f6-b66a-42fd-8d36-19338d4f6957" />

# Detecting SSH Attacks

## Questions

<img width="1580" height="175" alt="image" src="https://github.com/user-attachments/assets/fb0013d0-7dd0-4551-b0e4-21f35051fc9a" />

- Which four users did the botnet attempt to breach? ```root, roy, sol, user```

- Finally, which IP managed to breach the root user? ```91.224.92.79```

<img width="1446" height="111" alt="image" src="https://github.com/user-attachments/assets/5de519b2-e21b-424f-a194-9da11ef7a745" />


# Detecting Service Breach

- We should use process tree analysis, build a process tree and trace the command back to its parent process.

<img width="1543" height="391" alt="image" src="https://github.com/user-attachments/assets/bed628f9-8d2f-4931-9625-2c513b31143d" />

## Questions
- What is the PPID of the suspicious whoami command? ``1018``
- Moving up the tree, what is the PID of the TryPingMe app?
<img width="1889" height="244" alt="image" src="https://github.com/user-attachments/assets/1a6859f6-8982-4e01-a1a0-0a368fad782e" />
- Which program did the attacker use to open a reverse shell? ``python``

