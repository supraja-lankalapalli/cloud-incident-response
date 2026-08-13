# AWS Cloud Incident Response

## About This Project

I created this project to practice how security incidents and unauthorized activities can be investigated in an AWS environment.

Instead of only learning AWS security concepts, I wanted to perform the actions myself, review what AWS recorded, and understand how IAM permissions and CloudTrail can help during an investigation.

For this project, I used the AWS environment that I had already built and secured in my previous cloud security project.

---

## What I Worked On

In this project, I focused on two security investigations.

### CS-001 – CloudTrail Console Login Investigation

I used AWS CloudTrail to investigate a console login event.

I reviewed the event details to understand what information AWS records during authentication, including the event time, source IP address, AWS Region, event source, and request information.

This helped me understand how CloudTrail can be used to investigate account activity.

### CS-002 – IAM Least Privilege Investigation

For this case, I used a Developer IAM user with limited permissions.

The user was able to view EC2 resources, but I tested whether the same user could perform a write action by attempting to stop an EC2 instance.

AWS denied the action.

I then investigated the event in CloudTrail and found the `StopInstances` event with the error:

`Client.UnauthorizedOperation`

I reviewed the Developer user's IAM permissions and confirmed that the user had `AmazonEC2ReadOnlyAccess` through the Developers group along with the `SecurityAudit` policy.

This helped me understand how IAM least privilege and CloudTrail work together during a security investigation.

---

## AWS Services Used

- AWS IAM
- AWS CloudTrail
- Amazon EC2

---

## Security Skills Practiced

- Cloud incident investigation
- AWS audit log analysis
- IAM least privilege
- Authentication monitoring
- Unauthorized API activity investigation
- Security event validation
- Evidence collection
- Incident documentation

---

## Security Cases

Detailed investigation notes are available in the `security-cases` folder:

- `CS-001-CloudTrail-Console-Login-Investigation.md`
- `CS-002-IAM-Least-Privilege-Investigation.md`

---

## Project Evidence

I included screenshots from my AWS environment in the `screenshots` folder to show the configurations and investigation results used in each case.

The evidence includes:

- IAM security permissions
- CloudTrail configuration
- CloudTrail Event History
- Console login investigation
- Developer access denial
- Unauthorized `StopInstances` CloudTrail event
- Developer IAM permissions

---

## What I Learned

This project helped me understand that incident response is not only about seeing an error or alert. I need to investigate what happened, identify which user performed the action, review the permissions involved, and use logs to confirm the activity.

The most useful part for me was seeing how CloudTrail and IAM work together. IAM controls what a user is allowed to do, while CloudTrail gives me the evidence to investigate what the user attempted to do.