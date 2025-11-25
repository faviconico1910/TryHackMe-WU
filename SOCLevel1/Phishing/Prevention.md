# Phishing Prevention
## Sender Policy Framework (SPF)
Sender Policy Framework (SPF) is used to authenticate the sender of an email. With an SPF record in place, Internet Service Providers can verify that a mail server is authorized to send email for a specific domain. An SPF record is a DNS TXT record containing a list of the IP addresses that are allowed to send email on behalf of your domain.

<img width="1490" height="284" alt="image" src="https://github.com/user-attachments/assets/aca1dad6-b3e7-4f99-bf88-b0dd102a10ef" />


Example of SPF Record: ```v=spf1 ip4:127.0.0.1 include:_spf.google.com -all```

## DomainKeys Identified Mail (DKIM)
DKIM stands for DomainKeys Identified Mail and is used for the authentication of an email that’s being sent. Like SPF, DKIM is an open standard for email authentication that is used for DMARC alignment. A DKIM record exists in the DNS, but it is more complex than SPF. DKIM’s advantage is that it can survive forwarding, which makes it superior to SPF and a foundation for securing your email

Example of DKIM Record: ```v=DKIM1; k=rsa; p=<public_key>```

## Domain-Based Message Authentication, Reporting, and Conformance (DMARC)
DMARC, an open source standard, uses a concept called alignment to tie the result of two other open source standards,  SPF (a published list of servers that are authorized to send email on behalf of a domain) and DKIM (a tamper-evident domain seal associated with a piece of email), to the content of an email.

Example of DMARC Record: ```v=DMARC1; p=quarantine; rua=mailto:postmaster@website.com```

## Secure/Multipurpose Internet Mail Extensions (S/MIME)

The two main components and security features of S/MIME are:

### Digital Signatures

Authentication: Confirms the sender's identity through their digital certificate

Non-repudiation: Ensures the sender cannot deny sending the message

Data Integrity: Detects any changes to the message after it's signed

### Encryption
Confidentiality: Keeps the content private and readable only by the intended recipient

Data Integrity: Detects any changes during message transmission
