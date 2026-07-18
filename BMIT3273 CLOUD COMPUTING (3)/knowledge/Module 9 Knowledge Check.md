# Module 9: Advanced Security — Knowledge Check

---

## 1. Which are characteristics of an AWS Identity and Access Management (IAM) group? (Select TWO)

### **Answer**

- New users added to a group inherit the group's permissions. ✅
- A user can belong to more than one group. ✅

### **Keywords to remember for MCQ**

- IAM Group
- Users inherit group permissions
- User can belong to multiple groups
- Groups cannot belong to other groups
- No security credentials for groups

### **Explanation**

When a new user is added to an IAM group, they automatically **inherit all permissions** attached to that group. Users can also be members of **multiple groups** simultaneously, allowing flexible permission management. Groups **cannot** belong to other groups, **cannot** have security credentials, and group policy permissions don't automatically override user policy permissions.

---

## 2. What is an advantage of using attribute-based access control (ABAC) over role-based access control (RBAC)?

### **Answer**

ABAC will likely require fewer policies than RBAC.

### **Keywords to remember for MCQ**

- ABAC vs RBAC
- Fewer policies needed
- Attribute-based
- Role-based
- Scales better

### **Explanation**

**ABAC** uses **attributes** (like department, project, or environment) to grant access, meaning you can write a **single policy** that works across many scenarios. **RBAC** requires a separate policy for each role. For example, with ABAC one policy can say "users can only access resources tagged with their project name," while RBAC would need separate policies for each project role. ABAC scales better as the organization grows.

---

## 3. A developer is a member of an IAM group. Group policy allows S3 and EC2, denies ECS. Developer also has a user policy allowing ECS and CloudFront. What access does the developer have?

### **Answer**

Access to Amazon S3, Amazon EC2, and Amazon CloudFront, but no access to Amazon ECS.

### **Keywords to remember for MCQ**

- Group policy + user policy
- Deny in group policy overrides allow in user policy
- Explicit deny always wins
- S3 + EC2 allowed
- ECS denied (explicit deny wins)
- CloudFront allowed (user policy)

### **Explanation**

In AWS IAM, **explicit deny always wins** over any allow. The group policy explicitly **denies** ECS access, so even though the user policy **allows** ECS, the deny overrides it. The user gets S3 and EC2 from the group policy, CloudFront from the user policy, but **not** ECS. This is a critical IAM concept for exams.

---

## 4. What is a benefit of identity federation with the AWS Cloud?

### **Answer**

It enables the use of an external identity provider to authenticate workforce users and give them access to AWS resources.

### **Keywords to remember for MCQ**

- Identity federation
- External identity provider
- Authenticate workforce users
- No need for IAM users
- SAML, OIDC

### **Explanation**

**Identity federation** allows users to authenticate through an **external identity provider** (like Active Directory, Google, or Facebook) and then access AWS resources **without needing IAM credentials**. This simplifies user management, enables single sign-on, and leverages existing corporate identity systems.

---

## 5. Which service enables identity federation for accessing a web application running in the AWS Cloud?

### **Answer**

Amazon Cognito.

### **Keywords to remember for MCQ**

- Amazon Cognito
- Identity federation
- Web application
- User pools
- Identity pools

### **Explanation**

**Amazon Cognito** provides **user pools** (for sign-in/sign-up) and **identity pools** (for granting AWS credentials) to enable identity federation for web and mobile apps. AWS WAF is a web firewall, KMS is for encryption keys, and CloudHSM is for hardware security modules — none handle user federation.

---

## 6. Which service helps centrally manage billing, control access, compliance and security, and share resources across multiple AWS accounts?

### **Answer**

AWS Organizations.

### **Keywords to remember for MCQ**

- AWS Organizations
- Multi-account management
- Centralized billing
- Service Control Policies (SCPs)
- Resource sharing

### **Explanation**

**AWS Organizations** provides **centralized management** for multiple AWS accounts, including billing consolidation, access control via **SCPs**, compliance enforcement, and **resource sharing** across accounts. IAM handles individual account permissions, Systems Manager is for operations, and Cognito is for app user management.

---

## 7. A company wants to prevent all IAM users in production accounts from deleting CloudTrail logs. How can a system administrator enforce this?

### **Answer**

Create a service control policy (SCP), and attach it to the production OU.

### **Keywords to remember for MCQ**

- SCP (Service Control Policy)
- Attached to OU
- Prevents CloudTrail deletion
- Organization-wide enforcement
- SCP limits maximum permissions

### **Explanation**

**SCPs** are attached to **Organizational Units (OUs)** or accounts and act as **permission boundaries** for all users in that scope. An SCP attached to the production OU can **deny** the `cloudtrail:DeleteTrail` action, preventing any user in those accounts from deleting logs — regardless of their individual IAM policies.

---

## 8. A developer encrypts data with a data key before sending to a server. The data key is sent alongside. The developer is concerned about data key theft. Which encryption type?

### **Answer**

Envelope encryption.

### **Keywords to remember for MCQ**

- Envelope encryption
- Data key encrypted by master key
- Two-layer protection
- KMS envelope encryption
- Data key + encrypted data key

### **Explanation**

**Envelope encryption** encrypts data with a **data key**, then encrypts the data key itself with a **master key** (like an AWS KMS key). Even if the encrypted data key is intercepted, it's useless without the master key. The server decrypts the data key using KMS, then uses it to decrypt the data. This provides **two-layer protection**.

---

## 9. Which functions does the AWS Key Management Service (AWS KMS) provide? (Select TWO)

### **Answer**

- Rotate keys ✅
- Create symmetric and asymmetric keys ✅

### **Keywords to remember for MCQ**

- AWS KMS
- Key rotation
- Symmetric and asymmetric keys
- Managed keys
- Cannot store encrypted data

### **Explanation**

AWS KMS can **automatically rotate** customer-managed keys and supports creating both **symmetric** (same key for encrypt/decrypt) and **asymmetric** keys (public/private key pair). KMS does **not** authenticate external users, create IAM access keys, or store encrypted data directly — it only manages encryption keys.

---

## 10. Which AWS service discovers and protects sensitive information stored on Amazon S3 in an AWS account?

### **Answer**

Amazon Macie.

### **Keywords to remember for MCQ**

- Amazon Macie
- Discovers sensitive data on S3
- PII detection
- S3 bucket monitoring
- Machine learning

### **Explanation**

**Amazon Macie** uses **machine learning** and pattern matching to automatically discover, classify, and protect **sensitive data** (like PII and financial data) stored in S3 buckets. Detective is for security investigations, RAM is for resource sharing, and Audit Manager is for compliance auditing — none focus on sensitive data discovery in S3.
