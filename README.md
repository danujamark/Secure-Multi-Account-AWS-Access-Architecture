# Secure-Multi-Account-AWS-Access-Architecture
AWS multi-account architecture project implementing IAM roles, MFA enforcement, SCP policies, and secure cross-account access management.

## Overview

This project demonstrates the implementation of a secure multi-account AWS architecture using AWS Organizations.

The environment is designed with separate Development, Staging, and Production accounts to improve workload isolation, governance, and security management while following AWS best practices.

The project also implements Service Control Policies (SCPs), cross-account IAM role access, and MFA enforcement to strengthen organizational security.

---

## Architecture Components

- AWS Organizations
- Organizational Units (OU)
- Multi-Account Structure
- Service Control Policies (SCP)
- IAM Users & Roles
- Cross-Account Access
- MFA Enforcement
- Least Privilege Access Model

---

## Account Structure

```text
Root
└── Workloads
    ├── Dev Account
    ├── Staging Account
    └── Production Account
```

---

## Project Objectives

- Isolate environments using separate AWS accounts
- Implement centralized governance
- Restrict unauthorized service actions
- Enable secure cross-account administration
- Enforce Multi-Factor Authentication (MFA)
- Improve operational security and compliance

---

## Tasks Completed

### AWS Organization Setup
- Created AWS Organization
- Configured centralized management account

### Multi-Account Environment
- Created:
  - Dev Account
  - Staging Account
  - Production Account

### Organizational Unit Configuration
- Created Workloads OU
- Moved accounts into the organizational unit

### Service Control Policy (SCP)
- Created SCP to block:
  - CloudTrail deletion
  - CloudTrail logging disable actions

### IAM Configuration
- Created administrative IAM user
- Attached AdministratorAccess policy

### MFA Enforcement
- Enabled MFA using Google Authenticator
- Secured IAM user login process

### Cross-Account Access
- Created IAM role in Dev account
- Enabled role assumption from management account
- Configured trust relationships for secure access

---

## Example SCP Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": [
        "cloudtrail:DeleteTrail",
        "cloudtrail:StopLogging"
      ],
      "Resource": "*"
    }
  ]
}
```

---

## Security Features Implemented

- Multi-account isolation
- Centralized governance
- SCP-based service restrictions
- MFA enforcement
- IAM role assumption
- Least privilege access control

---

## Technologies Used

- AWS Organizations
- IAM
- SCP Policies
- MFA
- Cross-Account IAM Roles
- CloudTrail

---

## Learning Outcome

This project demonstrates practical knowledge of:

- AWS multi-account governance
- Organizational Unit management
- Service Control Policies
- Secure IAM practices
- Cross-account access architecture
- MFA-based identity protection
- Enterprise-grade AWS security design
