# AWS CloudFormation IAM Role and Policy Template
---

This template is used to create an IAM Role and an IAM Policy.  The IAM Role, by default, is meant to be assumed by one or more IAM Users.  The IAM Policy associated with the role provides read-only access to all log groups and log streams assocated with the AWS account.

<br />

## Template Parameters

|  Parameter Name | Description | Constraints | Required? |
|----------------|-------------|-------------|-----------|
| **ManagedPolicy** | The name of the Managed Policy to associate with the IAM Role | Must be one of the AllowedValues | No |
| **Path** | The IAM Path to associate with the IAM Role | Should be a hierarchical path-based string with a forward slash delimiter, and must start and end with "/" | No -- Defaults to "/" |
| **PolicyName** | The name of the IAM Policy | Must be a String value and conform to the following regular expression: ^[a-zA-Z][a-zA-Z0-9_+=,.@-]{1,64}$ | Yes |
| **RoleName** | The name of the IAM Role | Must be a String value that conforms to the following regular expression: ^[a-zA-Z][a-zA-Z0-9]{1,64}$ | Optional - leave value set to "None" to allow IAM to dynamically name the role |

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
* Actions, Resources, and Condition Keys for AWS Resources: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_actions-resources-contextkeys.html
* AWS CloudFormation Best Practices: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/best-practices.html
* AWS::IAM::Policy CloudFormation Resource: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-policy.html
* AWS::IAM::Role CloudFormation Resource: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-resource-iam-role.html
* Cloudonaut Complete AWS IAM Reference: https://iam.cloudonaut.io/reference/#/
* How IAM Roles Differ from Resource-based Policies: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_compare-resource-policies.html
* IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
* IAM JSON Policy Reference: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html
* IAM Roles: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html
* Policies and Permissions: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html
* Tagging IAM Entities: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_tags.html
* Understanding Permissions Granted by a Policy: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_understand.html