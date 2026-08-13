# CS-002: IAM Least Privilege Investigation

## Objective

I wanted to check what happens when an IAM user has limited permissions and tries to perform an action that is not allowed.

For this test, I used the Developer IAM user.

## What I Did

I logged in to AWS as the Developer user and checked the EC2 instances.

The Developer user was able to view the EC2 instances because the user has AmazonEC2ReadOnlyAccess.

I then tried to stop App-Server-01.

The stop action was denied because the Developer user did not have permission to stop EC2 instances.

## Investigation

After the denied action, I checked CloudTrail Event history.

CloudTrail recorded the StopInstances attempt from the Developer user.

The event showed:

* Event name: StopInstances
* User: Developer
* AWS Region: us-east-2
* Error code: Client.UnauthorizedOperation
* Read-only: false

I then checked the Developer user's IAM permissions.

The Developer user had AmazonEC2ReadOnlyAccess through the Developers group and SecurityAudit attached directly.

## What I Found

The Developer user could view EC2 resources but could not stop the EC2 instance.

This showed that the least privilege permissions were working correctly. The user had enough access to inspect resources without having permission to make this change.

CloudTrail also gave me evidence of the denied StopInstances attempt, which helped me identify which user attempted the action and what AWS denied.

## Evidence

* 05-developer-access-denied.png
* 06-cloudtrail-stopinstances-denied.png
* 07-developer-permissions.png

## What I Learned

This case helped me understand how IAM permissions and CloudTrail can be used together during an investigation.

IAM controls what a user is allowed to do, while CloudTrail helps investigate the actions that were attempted in the AWS account.
