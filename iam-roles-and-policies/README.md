# AWS Cross-Account IAM Role with AdministratorAccess Policy atatchement with terraform
---

This document describes how cross-account access is estableshed, and how AdministratorAccess policy is attached. The IAM Role, by default, is meant to be assumed by one or more IAM Users.  The IAM Policy associated with the role provides full admin access to all team members assocated with the shared AWS account.

<br />

## Template Parameters

|  Parameter Name | Description | 
|----------------|-------------|
| **Cli access establishemnt** | Must use provided IAM username by IAM admin | 
| **Shared account access** | Must assume provided role using your personal account | 
| **PolicyName** | AdministratorAccess | 
| **RoleName** | scrum_account_access | 

<br />

 ## Authors
 ---
* andron1x ( Andrew A)

<br />

