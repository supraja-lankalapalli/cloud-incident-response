# CS-001 – CloudTrail Console Login Investigation

## Objective

The goal of this case was to learn how AWS CloudTrail records console login events and how those logs can be used during a security investigation.

---

## What I Did

To begin, I created an IAM user and attached the SecurityAudit policy. After that, I created a multi-region CloudTrail trail to start collecting management events.

Once CloudTrail was active, I opened the Event History page and searched for the ConsoleLogin event. I then reviewed the event details to understand what information AWS records when someone signs in to the AWS Management Console.

---

## What I Found

From the ConsoleLogin event, I was able to see:

- Event name
- Event source
- Event time
- AWS Region
- Source IP address
- Request ID

I also noticed that no AWS resources were modified during this event because it was only a login activity.

---

## Evidence

- Screenshot 01 – IAM SecurityAudit policy
- Screenshot 02 – CloudTrail trail created successfully
- Screenshot 03 – CloudTrail Event History
- Screenshot 04 – ConsoleLogin event details

---

## Skills I Practiced

- AWS IAM
- AWS CloudTrail
- Cloud security monitoring
- Security event investigation
- Documentation of security findings

---

## What I Learned

This case helped me understand how CloudTrail records authentication activities in AWS. I learned where to find login events, how to review the event details, and how this information can be useful during a security investigation.