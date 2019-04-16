# AWS CloudFormation IAM Group Template
---

This template is used to create a stack that implements a single IAM Group.  The group can be associated with one of several Manged Policies offered by AWS.  Each managed policy maps to a traditional user job function/role. The stack exports both the group name and ARN on successful deployment.

<br />

## Template Parameters
---
|  Parameter Name | Description | Constraints | Required? |
|----------------|-------------|-------------|-----------|
| **GroupName** | The name of the IAM Group | Must be a String value | Yes |
| **ManagedPolicy** | The name of the Managed Policy to associate with the IAM Group | Must be one of the AllowedValues | No |
| **Path** | The IAM Path to associate with the IAM Group | Should be a hierarchical path-based string with a forward slash delimiter that matches the following regular expression: (^\/$)\|(^\/.*\/$) | No -- Defaults to "/" |

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
* AWS::IAM::Group CloudFormation Resource: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-iam-group.html
* IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
* IAM Business Use Cases: https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_UseCases.html
* IAM Identifiers: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html
* AWS Managed Policies for Job Functions: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html
* IAM Groups: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html
* Limitations on IAM Entities and Objects: https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-limits.html