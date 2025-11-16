# Alert Reporting

## Task 2: Alert Funnel

Alert Reporting:  document your investigation in detail, ensuring all relevant evidence is included. This is especially important for True Positives, which require escalation.

Alert Escalation: If the True Positive alert requires additional actions or deeper investigation, escalate it to the L2 analyst for further review following the agreed procedures


## Task 3: Reporting Guide
- Provide context for escalation
- Save findings for the records
- Improve investigation skills

Follow the Five Ws approach
- Who: Which user logs in, runs the command, or downloads the file
- What: What exact action or event sequence was performed
- When: When exactly did the suspicious activity start and ended
- Where: Which device, IP, or website was involved in the alert
- Why: The most important W, the reasoning for your final verdict

Question:
- According to the SOC dashboard, which user email leaked the sensitive document? ```m.boslan@tryhackme.thm```
- Looking at the new alerts, who is the "sender" of the suspicious, likely phishing email?
- Open the phishing alert, read its details, and try to understand the activity.
Using the Five Ws template, what flag did you receive after writing a good report? ```THM{nice_attempt_faking_microsoft_support}```

## Task 4: Escalation Guide
To escalate the alert, in most cases, all you have to do is to reassign the alert to the L2 on shift and ping them in corporate chat or in person. In some teams though, you may be required to create a formal written escalation request with dozens of required fields.

Question:
- Who is your current L2 in the SOC dashboard that you can assign (escalate) the alerts to? ```E.Fleming```
- What flag did you receive after correctly escalating the alert from the previous task to L2? ```THM{good_job_escalating_your_first_alert}```
- Now, investigate the second new alert in the queue and provide a detailed alert comment.
Then, decide if you need to escalate this alert and move on according to the process.
After you finish your triage, you should receive a flag, which is your answer! ```THM{looks_like_webshell_via_old_exchange}```

## Task 5: Communication
