# CloudFormation Templates for creating and maintaining IAM Resources
---
The templates in this repository are meant to be examples of how to create and manage basic IAM resources using CloudFormation. The examples, as pictured below, are divided into three separate groups by directory: IAM Groups, IAM Roles and Policies, and IAM Users.  Under each directory template examples associated with that IAM Resource type can be found.  

```
.
├── iam-groups
│   └── iam-group.yaml
├── iam-roles-and-policies
│   └── role-and-policy.yaml
└── iam-users
    ├── iam-user-with-access-key.yaml
    └── iam-user.yaml
```
<br />

### Template Files

* [IAM User Template Documentation](iam-users/README.md)
* [IAM Group Template Documentation](iam-groups/README.md)
* [IAM Role and Policy Documentation](iam-roles-and-policies/README.md)

<br />

## Deploying Templates via the AWS CLI
---
Prior to deploying your template from the AWS CLI, you'll need to create two files.  The first of these is the `tags.json` file that designates all of the resource tags to apply to the AWS Resources you are instantiating with your CloudFormation stack.  The second is your parameters.json file that is used to supply the CloudFormation parameter values to your template at time of deployment.

You can create a CloudFormation stack in one of two ways:

1. `aws cloudformation create-stack`
2. `aws cloudformation deploy`

The create-stack command uses the provided template to immediately instantiate a CloudFormation stack.  The deploy command, by default, uses the template to create a change-set and then immediately deploys the change-set as a CloudFormation stack.  The default behavior of the deploy command can be alterred to create a change set and pause prior to executing the change-set to deploy the CloudFormation stack.  The deploy command can also be executed against an existing CloudFormation stack to perform updates against that stack.

<br />

### **Tags**

There is a notable difference in the format of your tags.json file when performing an `aws cloudformation deploy` versus creating a CloudFormation stack using `aws cloudformation create-stack` command.


"*create-stack*" tags.json file format:
```
[
    {
        "Key": "Business_Unit",
        "Value": "1Strategy"
    },
    {
        "Key": "Owner",
        "Value": "Jane Doe"
    },
    {
        "Key": "Project"
        "Value": "IAM Resources"
    }
]
```

"*deploy*" tags.json file format:
```
[
    "Business_Unit=1Strategy",
    "Owner=Jane Doe",
    "Project=IAM Resources"
]
```

<br />

### **Parameters**

If your template deployment is referencing parameters at the command line, there is a difference on how they are consumed via an ``aws cloudformation deploy`` command, and an ``aws cloudformation create-stack`` command.

"*create-stack*" parameters.json file example:
```
[
    {
        "ParameterKey": "Username",
        "ParaemterValue": "Jane Doe"
    },
    {
        "ParameterKey": "ManagedPolicy",
        "ParameterValue": "SupportUser"
    }
]
```

"*deploy*" parameters.json example:
```
[
    "Username=Jane Doe",
    "ManagedPolicy=SupportUser"
]
```

<br />

### **Deploy**

Initialize the CloudFormation stack:

```
aws cloudformation create-stack \
    --template-body file://deployment.yaml \
    --stack-name jane-doe-iam-resources \
    --parameters file://parameters.json \
    --tags file://tags.json
    --region us-west-2 \
    --capabilities CAPABILITY_NAMED_IAM
```

```
aws cloudformation deploy \
    --template-file deployment.yaml \
    --stack-name jane-doe-iam-resources \
    --parameter-overrides file://parameters.json
    --tags file://tags.json \
    --region us-west-2 \
    --capabilities CAPABILITY_NAMED_IAM
```
    

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
* AWS CLI cloudformation create-stack: https://docs.aws.amazon.com/cli/latest/reference/cloudformation/create-stack.html
* AWS CLI cloudformation deploy: https://docs.aws.amazon.com/cli/latest/reference/cloudformation/deploy/index.html
* AWS CloudFormation Best Practices: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/best-practices.html
* AWS CloudFormation Template Reference: https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-reference.html
* Cloudonaut Complete IAM Reference: https://iam.cloudonaut.io/reference/#/
* IAM Best Practices: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html