# Identity Access Management (IAM)

IAM is a global AWS service (that is, IAM Users, Groups etc. are available across all regions).

## Fundamentals of IAM

IAM consists of several entities:

- Users, which should have a one to one correspondence with real people.
- Groups, which can contain users (but not groups).
  - There is a many to many map between users and groups.
  - A user with no groups is also valid.

Permissions can be set for users or groups via policy documents (defined in JSON format).
- The structure of a policy document is outlined here: https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-policy-structure.html
- If multiple policies apply to the same action for one user, the logic for determining which takes precedence is outlined here: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_evaluation-logic.html

Side Note: The _Principle of Least Privilege_ states that you should never give a user or group more permissions than they need.
- This implies the Root account assigned by default when you sign up should never be passed around, and in fact shouldn't be used once you've set up an ordinary user. It has essentially maximum permissions, which is too many.

## Logging in

Since IAM users come with a set of permissions, we need to control who can act as an IAM user. To do this, you should:

1. Set a _password policy_, to make sure IAM users on your account have passwords that are sufficiently strong, frequently changing, etc.

2. Set up multifactor authentication on all your root account + all important IAM users.