<img width="829" height="537" alt="image" src="https://github.com/user-attachments/assets/c3cf0c92-0dd7-494c-998f-d299f90c6191" />
# OWASP Top 10 - 2021



## Broken Access Control (IDOR Challenge)
Broken access control allows attackers to bypass authorisation, allowing them to view sensitive data or perform tasks they aren't supposed to

- Login with username and password provided. Then, we can see that the server responses to the browser through parameter, so changing it may give us flag.

<img width="1695" height="631" alt="image" src="https://github.com/user-attachments/assets/bf85ca5c-5c26-4cd8-82f1-166cda21f241" />

***FLAG***: ```flag{fivefourthree}```

## Cryptography Failures
A cryptographic failure refers to any vulnerability arising from the misuse (or lack of use) of cryptographic algorithms for protecting sensitive information.

"flat-file" databases: data is stored as a single file on the computer. The most common (and simplest) format of a flat-file database is an SQLite database
### Task 8: Cryptographic Failures (Challenge)
- What is the name of the mentioned directory? ```assets```
- Navigate to the directory you found in question one. What file stands out as being likely to contain sensitive data? ```webapp.db```
- What is the password hash of the admin user? ```6eea9b7ef19179a06954edd0f6c05ceb```
<img width="649" height="145" alt="image" src="https://github.com/user-attachments/assets/5aca5dd5-f3c3-4f40-a462-9e23c93cd45a" />

- What is the admin's plaintext password? ```qwertyuiop```
<img width="709" height="317" alt="image" src="https://github.com/user-attachments/assets/2a8c2125-4979-4f17-8743-04b4f594f74f" />

Then, login as admin and get the flag.

***FLAG***: ```THM{Yzc2YjdkMjE5N2VjMzNhOTE3NjdiMjdl}```

## Injection
### Task 10: 
Question
- What strange text file is in the website's root directory? ```drpepper.txt```
- How many non-root/non-service/non-daemon users are there? ```0```
<img width="829" height="537" alt="image" src="https://github.com/user-attachments/assets/d9203f02-d4a7-4675-98e5-1462bc8efa65" />

