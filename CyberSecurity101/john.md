## Task 4: Crack Basic Hashes
Basic syntax: ```john --format=[format] --wordlist=[path to wordlist] [path to file]```

Questions:
- What type of hash is hash1.txt? ```md5```
- What is the cracked value of hash1.txt? ```biscuit```
- What type of hash is hash2.txt? ```sha1```
- What is the cracked value of hash2.txt? ```kangeroo```
- What type of hash is hash3.txt? ```sha256```
- What is the cracked value of hash3.txt? ```microphone```
- What type of hash is hash4.txt?```whirlpool```
- What is the cracked value of hash4.txt? ```colossal```

## Task 5: Cracking Windows Authentication Hashes

NTHash / NTLM: NThash is the hash format modern Windows operating system machines use to store user and service passwords (in SAM).
It’s also commonly referred to as NTLM, which references the previous version of Windows format for hashing passwords known as LM, thus NT/LM.

Questions:
- What do we need to set the --format flag to in order to crack this hash? ```nt```

- What is the cracked value of this password? ```mushroom```

## Task 6: Cracking /etc/shadow Hashes

Questions: ```1234```

## Task 7: Single Crack Mode

Syntax: ```john --single --format=[format] [path to file]```

Questions:
- What is Joker’s password? ```Jok3r```

## Task 8: Custom Rules
Custom rules are defined in the john.conf file. This file can be found in ```/opt/john/john.conf``` on the TryHackMe Attackbox.
It is usually located in ```/etc/john/john.conf``` if you have installed John using a package manager or built from source with make

Questions:
- What do custom rules allow us to exploit? ```Password complexity predictability```
- What rule would we use to add all capital letters to the end of the word? ```Az"[A-Z]"```
- What flag would we use to call a custom rule called THMRules? ```--rule=THMRules```

## Task 9: Cracking Password Protected Zip Files
Step 1: ```zip2john [options] [zip file] > [output file]```
Step 2: use ```john```

Questions: 
- What is the password for the secure.zip file? ```pass123```
- What is the contents of the flag inside the zip file? ```THM{w3ll_d0n3_h4sh_r0y4l}```

## Task 10: Cracking Password-Protected RAR Archives
Similar to zip2john: ```rar2john [rar file] > [output file]```

Questions:
- What is the password for the secure.rar file? ```password```
- What are the contents of the flag inside the zip file? ```THM{r4r_4rch1ve5_th15_t1m3}```

## Task 11: Cracking SSH Keys with John

Syntax: ```ssh2john [id_rsa private key file] > [output file]```

Questions:
- What is the SSH private key password? ```mango```
