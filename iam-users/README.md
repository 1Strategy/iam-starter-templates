# AWS CloudFormation IAM User Template
---
This template is used to provision a single IAM User account.  It provides the ability to associate the user account with multiple IAM Groups, as well as a predefined Role-based Service Policy.  It allows for supplying an optional Username for the IAM User account, as well as enforcing a required password reset on first login.  On successful deployment of the CloudFormation stack, the IAM User's Username and ARN are exported.

<br />

## Template Parameters
---
|  Parameter Name | Description | Constraints | Required? |
|----------------|-------------|-------------|-----------|
| **Group** | The name of an IAM group in which to add the new IAM user | Must be a comma separated list of IAM Group names | No |
| **ManagedPolicy** | The name of a Managed Policy to associate with the new IAM user | Must be one of the allowed values in the list available Managed policies | No |
| **Password** | The password for the IAM user | Must match the following regular expression: ^[a-zA-Z][a-zA-Z0-9!@#$%&]{8,32}$ | Yes |
| **PasswordResetRequired** | Designates whether a password reset is required by the IAM user on first login | Must be "true" or "false" | Yes |
| **Path** | The IAM Path to associate with the IAM user | Should be a hierarchical path-based string with a forward slash delimiter that matches the following regular expression: (^\/$)\|(^\/.*\/$) | Conditional -- defaults to "/" |
| **UserName** | The Username to associate with the new IAM user | Must match the following regular expression: ^[\w+=,.@-]{1,64}$ | No |

<br />

 ## Authors
 ---
* Will Nave - [1Strategy](https://www.1strategy.com)

<br />

## License
---
Copyright 2019 1Strategy

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

<br />

## References
---
* AWS CloudFormation Best Practices: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/best-practices.html
* AWS::IAM::User CloudFormation Resource: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-user.html
* AWS Managed Policies for Job Functions: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html
* IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
* IAM Business Use Cases: https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UseCases.html
* IAM Identifiers: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html
* IAM Users: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html
* Limitations of IAM Entities and Objects: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-limits.html
* Setting an Account Password Policy for IAM Users: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_passwords_account-policy.html
* Tagging IAM Entities: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_tags.html