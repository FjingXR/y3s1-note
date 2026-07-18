# Module 7: Creating a Networking Environment — Knowledge Check

---

## 1. Which definition describes a virtual private cloud (VPC)?

### **Answer**

A logically isolated virtual network that you define in the AWS Cloud.

### **Keywords to remember for MCQ**

- Virtual Private Cloud (VPC)
- Logically isolated
- Virtual network
- AWS Cloud

### **Explanation**

A VPC is a **logically isolated** virtual network that you create and control within AWS. It's not a VPN, not an extension of on-premises (that's Direct Connect/VPN), and not a fully managed service like Storage Gateway. Key features: you define your own IP address range, subnets, route tables, and network gateways.

---

## 2. Which component does not have direct access to the internet?

### **Answer**

EC2 instance inside a private subnet.

### **Keywords to remember for MCQ**

- Private subnet → no direct internet access
- Public subnet → has internet gateway route
- NAT gateway → outbound only
- Elastic IP → public IP

### **Explanation**

A **private subnet** has no route to an Internet Gateway — instances inside cannot be reached from the internet and cannot initiate outbound connections without a NAT gateway. A NAT gateway in a public subnet allows private subnet instances to reach the internet **outbound only**, but they still cannot be reached inbound from the internet.

---

## 3. A VPC has CIDR block 172.16.0.0/21 (2048 addresses). Two subnets (A and B) each need 100 usable now, rising to 254 usable soon. Which scheme meets requirements and follows best practices?

### **Answer**

Subnet A: 172.16.0.0/23 (512 addresses)
Subnet B: 172.16.2.0/23 (512 addresses)

### **Keywords to remember for MCQ**

- /23 = 512 addresses (253 usable)
- Leave room for growth
- Best practice: use same size subnets
- CIDR planning

### **Explanation**

/24 gives 256 addresses (251 usable) — enough for 254 usable but no room for growth. /25 gives 128 (121 usable) — not enough for 254. /22 gives 1024 — too wasteful. **/23 gives 512 addresses (513 usable)** — comfortably supports 254 usable with room for growth, and uses address space efficiently. Best practice: use the same subnet size across AZs for consistency.

---

## 4. Several EC2 instances in a VPC must not be accessible from the internet but must download updates. How should they launch?

### **Answer**

Without public IP addresses, in a subnet with a default route to a NAT gateway.

### **Keywords to remember for MCQ**

- Private subnet
- NAT gateway
- No public IP
- Outbound internet access only

### **Explanation**

Private subnet instances have no public IP → not reachable from the internet. A **NAT gateway** in the public subnet provides **outbound-only** internet access (for updates), while keeping instances unreachable inbound. Security groups add another layer of control.

---

## 5. Consultants need internet access to an EC2 instance for 3 consecutive days per week. Instance is shut down the rest. How should you assign the IPv4 address?

### **Answer**

Associate an Elastic IP address with the EC2 instance.

### **Keywords to remember for MCQ**

- Elastic IP (EIP)
- Static public IP
- Persists after stop/start
- Internet-accessible

### **Explanation**

An **Elastic IP** is a static public IP that stays associated with the instance even when stopped/started. This is ideal when you need consistent internet access that persists across instance state changes. Regular public IPs change after stop/start, making them unreliable for this scenario.

---

## 6. An application uses a bastion host to access EC2 instances in a private subnet. What security group configurations allow SSH from source IP to EC2? (Select TWO)

### **Answer**

- Add a rule to the EC2 instance security group to allow traffic from the bastion host security group on port 22. ✅
- Add a rule to the bastion host security group to allow traffic on port 22 from your source IP address. ✅

### **Keywords to remember for MCQ**

- Bastion host (jump box)
- Security group references
- SSH on port 22
- Two-tier security

### **Explanation**

**Bastion host SG**: Allow inbound SSH (22) from your source IP → you connect to the bastion first. **EC2 instance SG**: Allow inbound SSH (22) only from the bastion host SG → only the bastion can reach the instances. This two-tier approach ensures no direct internet access to private instances.

---

## 7. A solution needs a subnet with limited access to specific internet addresses. How can an architect configure network ACLs?

### **Answer**

Add rules to the subnet custom network ACL to allow traffic from and to allowed internet addresses.

### **Keywords to remember for MCQ**

- Network ACL (NACL)
- Stateless
- Subnet level
- Allow specific IPs
- Custom NACL

### **Explanation**

NACLs are **stateless** and operate at the **subnet level**. To limit traffic: create a custom NACL that explicitly **allows** traffic from/to specific internet addresses, then **denies** all other traffic. The default NACL allows all inbound/outbound — you can't restrict it. Custom NACLs replace the default rules entirely.

---

## 8. Which actions are best practices for designing a VPC? (Select THREE)

### **Answer**

- Reserve some address space for future use. ✅
- Create one subnet per AZ for each group of hosts that have unique routing requirements. ✅
- Divide the VPC network range evenly across all AZs that are available. ✅

### **Keywords to remember for MCQ**

- VPC design best practices
- Reserve address space
- One subnet per AZ per routing group
- Even AZ distribution
- Plan for growth

### **Explanation**

**Best practices**: (1) **Reserve address space** — don't use all CIDR addresses immediately; plan for growth. (2) **One subnet per AZ** for each routing/security group — this aligns with AZ-based redundancy. (3) **Divide evenly across AZs** — ensures balanced, predictable networking. Using the same CIDR for different AZs conflicts with overlapping ranges; matching VPC size exactly to workload leaves no room for growth.

---

## 9. Where can you have VPC flow logs delivered? (Select THREE)

### **Answer**

- Amazon CloudWatch ✅
- Amazon S3 bucket ✅
- Amazon Kinesis Data Firehose ✅

### **Keywords to remember for MCQ**

- VPC Flow Logs
- CloudWatch Logs
- S3 bucket
- Kinesis Data Firehose
- Network monitoring

### **Explanation**

VPC Flow Logs capture IP traffic metadata and can be sent to: **CloudWatch Logs** (for monitoring and alarms), **S3** (for long-term storage and analysis), or **Kinesis Data Firehose** (for real-time streaming to analytics services like S3, Redshift, or OpenSearch). Athena, OpenSearch, and Console are analysis tools, not delivery destinations.

---

## 10. An EC2 instance must connect to an S3 bucket. What provides connectivity with no additional charge and no throughput packet limits?

### **Answer**

Gateway VPC endpoint.

### **Keywords to remember for MCQ**

- Gateway VPC endpoint
- No additional charge
- No throughput limits
- S3 and DynamoDB only
- Private connectivity

### **Explanation**

A **Gateway VPC endpoint** provides private connectivity between your VPC and S3 (or DynamoDB) without going through the internet, with **no additional charge** and **no throughput limits**. Interface VPC endpoints are for other AWS services and have hourly charges + throughput limits. Gateway Load Balancer endpoints are for third-party virtual appliances.
