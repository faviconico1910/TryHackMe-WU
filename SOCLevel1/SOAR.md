# Introduction to SOAR

## Task 3: Overcoming SOC Challenges with SOAR (Security Orchestration, Automation, and Response)

1. Orchestration:

Coordinating all these tools together inside the SOAR, connecting different tools from various vendors within the unified SOAR interface,
defining workflows for investigating various types of alerts, known as ***Playbook***

2. Automation
3. Response
SOAR gives the ability to take actions using different tools from one unified interface. It also automates the response, as we saw earlier while looking at its Automation capability. For example, SOAR can follow the playbook of VPN Brute force and block the IP on the firewall, disable the user in the IAM, and open a ticket with all the details.

## Task 4: Building SOAR Playbooks

Question:
- From where is the CVE Patching playbook fetching the new CVEs? ```Advisory lists```
- In the CVE Patching playbook, if the assets are found vulnerable even after the patch is deployed, what does the SOC develop next? ```mitigation plan```


 ## Task 5: Threat Intel Workflow Practical

 ***Flag***: ```THM{AUT0M@T1N6_S3CUR1T¥}```
