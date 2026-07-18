# Module 11: Infrastructure Automation — Knowledge Check

---

## 1. Which are reasons to use automation to provision resources? (Select TWO)

### **Answer**

- Lack of version control with manual processes. ✅
- Alignment with the reliability design principle. ✅

### **Keywords to remember for MCQ**

- Automation reasons
- Version control
- Reliability principle
- Manual processes lack version control
- Infrastructure consistency

### **Explanation**

Manual processes lack **version control** — you can't easily track changes or roll back. Automation aligns with the **reliability design principle** by ensuring consistent, repeatable deployments. Automation is not necessarily more expensive, isn't required for some resources, and isn't strictly required for high availability.

---

## 2. Which are benefits of using infrastructure as code (IaC) over manual processes? (Select TWO)

### **Answer**

- Propagate updates from a single environment to all environments. ✅
- Deploy environments with configuration consistency. ✅

### **Keywords to remember for MCQ**

- IaC benefits
- Configuration consistency
- Single template → multiple environments
- Reproducible deployments
- Not related to user management or security scans

### **Explanation**

IaC lets you **define infrastructure once** and deploy it consistently across development, staging, and production. Changes propagate from a **single source** to all environments. IaC doesn't manage users, protect from deletion, or automate security scans directly.

---

## 3. A cloud architect wants to quickly set up a secure implementation of Amazon FSx for Windows File Server following AWS best practices. Which solution?

### **Answer**

An AWS Quick Start.

### **Keywords to remember for MCQ**

- AWS Quick Start
- Pre-built templates
- Best practices
- Fast deployment
- Vetted by AWS

### **Explanation**

**AWS Quick Starts** are pre-built, **vetted by AWS** CloudFormation templates that deploy popular architectures following **best practices**. They're the fastest way to set up secure implementations. Templates from the internet may not be secure, AMIs are for EC2 instances, and CloudFormation Designer is a visual editor.

---

## 4. What is Amazon Q Developer?

### **Answer**

An artificial intelligence (AI)-powered coding companion.

### **Keywords to remember for MCQ**

- Amazon Q Developer
- AI-powered
- Coding companion
- Code suggestions
- Not an IDE

### **Explanation**

**Amazon Q Developer** is an **AI-powered coding companion** that provides code suggestions, helps with debugging, and accelerates development tasks. It's not an IDE, not a set of reference architectures, and not a deployment template.

---

## 5. Which are reasons to use Amazon Q Developer? (Select TWO)

### **Answer**

- Accelerate coding tasks. ✅
- Enhance application security. ✅

### **Keywords to remember for MCQ**

- Amazon Q Developer uses
- Accelerate coding
- Security enhancements
- Not for HA automation
- Not for compliance testing

### **Explanation**

Amazon Q Developer helps **accelerate coding tasks** (code suggestions, reviews, debugging) and **enhances application security** (security scanning, vulnerability detection). It's not designed for HA automation, compliance testing, or sharing open-source code.

---

## 6. What is AWS CloudFormation?

### **Answer**

An AWS service that you can use to create, model, and manage AWS resources.

### **Keywords to remember for MCQ**

- AWS CloudFormation
- Create, model, manage resources
- Infrastructure as Code service
- Templates define infrastructure
- Manages entire resource lifecycle

### **Explanation**

**AWS CloudFormation** is an **IaC service** that lets you define AWS resources in templates and manages their entire lifecycle — creation, updates, and deletion. A template is just the file format, not the service. An AMI is a machine image. Best practices are guidelines, not a service.

---

## 7. What is AWS CloudFormation Designer?

### **Answer**

A graphical design interface for creating AWS CloudFormation templates.

### **Keywords to remember for MCQ**

- CloudFormation Designer
- Graphical interface
- Visual template creation
- Drag and drop
- Not a source code repo

### **Explanation**

**CloudFormation Designer** is a **visual, drag-and-drop tool** in the AWS Management Console for creating CloudFormation templates. It shows resource relationships as a diagram. It's not a collection of templates, not a deployment automation tool, and not a source code repository.

---

## 8. Which option can be used to accomplish deployment-specific differences in a CloudFormation template?

### **Answer**

Use conditions.

### **Keywords to remember for MCQ**

- CloudFormation conditions
- Deployment-specific differences
- If/else logic in templates
- Conditional resource creation
- Not Designer, change sets, or drift

### **Explanation**

**Conditions** in CloudFormation let you define **if/else logic** — creating or skipping resources based on parameters, environment, or other values. Change sets preview changes, Designer is visual editing, and drift detection finds manual modifications.

---

## 9. Which is a good way to preview changes before implementing them in CloudFormation Designer?

### **Answer**

Create a change set.

### **Keywords to remember for MCQ**

- Change set
- Preview changes before applying
- See what will be created/modified/deleted
- Safe testing
- Not drift detection

### **Explanation**

A **change set** shows you **exactly what will change** (resources created, modified, or deleted) before you execute the update. It's the safe way to preview. Drift detection finds manual modifications after deployment. Update Stack applies changes immediately. Visual inspection doesn't show all changes.

---

## 10. Which option is a good way to know which resources in a CloudFormation environment were manually modified?

### **Answer**

Run drift detection on the stack.

### **Keywords to remember for MCQ**

- Drift detection
- Finds manual modifications
- Compares actual vs expected state
- CloudFormation stacks
- Not Designer or conditions

### **Explanation**

**Drift detection** compares the **actual resource state** against the **expected state** defined in the CloudFormation template. It identifies resources that were **manually modified** outside of CloudFormation. Change sets preview future changes, not past modifications. Designer and conditions don't detect drift.
