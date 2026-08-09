# AWS Cloud Incident Response & IAM Security Lab

## About This Project

I built this project to get hands-on experience with AWS security monitoring,
incident investigation, and IAM access control.

Instead of only learning AWS security concepts, I created a small AWS
environment where I could generate activity, investigate it through
CloudTrail, and test how IAM permissions affect what a user can do.

The project contains two security cases based on activities I performed
inside my AWS environment.

## What I Worked With

- AWS CloudTrail
- AWS IAM
- Amazon EC2
- IAM users and groups
- AWS managed policies
- Least-privilege access
- CloudTrail event history
- Access-denied investigation

## Security Cases

### CS-001 — CloudTrail Console Login Investigation

In this case, I configured AWS CloudTrail and used the event history to
investigate console login activity.

I reviewed the event details to understand who performed the activity,
when it happened, and where the request came from.

[View CS-001 Investigation](security-cases/CS-001-CloudTrail-Console-Login-Investigation.md)

### CS-002 — IAM Least-Privilege Investigation

In this case, I created a Developer IAM user with limited EC2 permissions.

I tested the permissions by attempting to stop an EC2 instance. The action
was denied because the Developer user did not have permission to stop
instances.

I then investigated the denied StopInstances event in CloudTrail and
confirmed that the action was blocked by IAM.

[View CS-002 Investigation](security-cases/CS-002-IAM-Least-Privilege-Investigation.md)

## What I Learned

Through this project, I practiced how to:

- Configure CloudTrail for AWS activity logging
- Investigate AWS console activity
- Review CloudTrail event details
- Work with IAM users, groups, and policies
- Apply least-privilege permissions
- Investigate denied AWS API actions
- Connect IAM permissions with CloudTrail evidence

## Project Evidence

Screenshots from the AWS environment are included in the `screenshots`
folder to show the configuration, testing, and investigation steps.

## Future Development

As I continue learning cloud security, I plan to expand this project with
additional monitoring and incident-response scenarios when they add
meaningful security value.