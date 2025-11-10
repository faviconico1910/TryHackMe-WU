# OWASP Top 10 - 2021

## 1. Broken Access Control (IDOR Challenge)
Broken access control allows attackers to bypass authorisation, allowing them to view sensitive data or perform tasks they aren't supposed to

- Login with username and password provided. Then, we can see that the server responses to the browser through parameter, so changing it may give us flag.

<img width="1695" height="631" alt="image" src="https://github.com/user-attachments/assets/bf85ca5c-5c26-4cd8-82f1-166cda21f241" />

***FLAG***: ```flag{fivefourthree}```

## 2. Cryptography Failures
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

## 3. Injection
### Task 10: 
Question
- What strange text file is in the website's root directory? ```drpepper.txt```
- How many non-root/non-service/non-daemon users are there? ```0```
<img width="829" height="537" alt="image" src="https://github.com/user-attachments/assets/d9203f02-d4a7-4675-98e5-1462bc8efa65" />

- What user is this app running as? ```apache```

- What is the user's shell set as? ```/sbin/nologin```
<img width="664" height="456" alt="image" src="https://github.com/user-attachments/assets/9212eaed-5972-4bc8-b602-36cde1c97def" />

- What version of Alpine Linux is running? ```3.16.0```
<img width="627" height="522" alt="image" src="https://github.com/user-attachments/assets/1e2211e4-e905-4c1c-b082-7e6da1469cd9" />

## 4. Insecure Design
Question: Try to reset joseph's password. Keep in mind the method used by the site to validate if you are indeed joseph.

When we visit the reset password questions, there are 3 questions available, and we'll realize that the question about color can be bruteforced. Try some colors to reset password, then login with the password reset, flag will be placed in the flag.txt.

<img width="1008" height="318" alt="image" src="https://github.com/user-attachments/assets/38b2d76d-4537-4055-b68e-809ab73c2b67" />


## 5. Security Misconfigurations

### Task 12:
Question:
- What is the database file name (the one with the .db extension) in the current directory? ```todo.db```
- What is the value of the secret_flag variable in the source code? ```THM{Just_a_tiny_misconfiguration}```

<img width="705" height="414" alt="image" src="https://github.com/user-attachments/assets/80379abe-27a4-42a8-874b-841fc6d99172" />

## 6. Vulnerable and Oudated Components

### Task 15: 
This vulnerability is ```Unrestricted File Upload``` which let the attacker upload the webshell, leading to RCE.

- ```What is the content of the /opt/flag.txt file?  ```THM{But_1ts_n0t_my_f4ult!}```


## 7. Identification and Authentication Failures Pratical

### Task 17:
- What is the flag that you found in darren's account? ```fe86079416a21a3c99937fea8874b667```
- What is the flag that you found in arthur's account? ```d9ac0f7db4fda460ac3edeb75d75e16e```

## 8. Software and Data Integrity Failures
This vulnerability arises from code or infrastructure that uses software or data without using any kind of integrity checks

### Task 19
- What is the SHA-256 hash of https://code.jquery.com/jquery-1.12.4.min.js? ```sha256-ZosEbRLbNQzLpnKIkEdrPv7lOy9C27hHQ+Xp8a4MxAQ=```

### Task 20
A data integrity failure vulnerability was present on some libraries implementing JWTs a while ago. As we have seen, JWT implements a signature to validate the integrity of the payload data. The vulnerable libraries allowed attackers to bypass the signature validation by changing the two following things in a JWT:

1. Modify the header section of the token so that the alg header would contain the value none.
2. Remove the signature part.

Question:
- What is the name of the website's cookie containing a JWT token? ```jwt-session```

Modify our decoded jwt header and payload and encode it again, remember to put the dot at the end of the cookie, then apply new cookie in the browser and refresh the site.

<img width="1704" height="512" alt="image" src="https://github.com/user-attachments/assets/4e448ec6-c6be-41a2-9113-9c719129458c" />

- What is the flag presented to the admin user? ```THM{Dont_take_cookies_from_strangers}```

## 9. Security Logging and Monitoring Failures

Question:
- What IP address is the attacker using? ```49.99.13.16```
- What kind of attack is being carried out? ```Brute Force```

## 10. Server-Side Request Forgery (SSRF)
This type of vulnerability occurs when an attacker can coerce a web application into sending requests on their behalf to arbitrary destinations while having control of the contents of the request itself. SSRF vulnerabilities often arise from implementations where our web application needs to use third-party services.

Question:
- Explore the website. What is the only host allowed to access the admin area? ```locahost```
- Check the "Download Resume" button. Where does the server parameter point to? ```secure-file-storage.com```
- Using SSRF, make the application send the request to your AttackBox instead of the secure file storage. Are there any API keys in the intercepted request? ```THM{Hello_Im_just_an_API_key}```

<img width="799" height="135" alt="image" src="https://github.com/user-attachments/assets/acd67630-cf2d-4554-94e5-b7414696ff6d" />







