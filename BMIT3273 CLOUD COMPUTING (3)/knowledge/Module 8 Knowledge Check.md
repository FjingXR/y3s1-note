# Module 8: Connecting Networks — Knowledge Check

---

## 1. What is the simplest way to connect 100 virtual private clouds (VPCs) together?

### **Answer**

Connect the VPCs to AWS Transit Gateway.

### **Keywords to remember for MCQ**

- Transit Gateway
- Hub-and-spoke
- Scalable
- 100+ VPCs

### **Explanation**

**AWS Transit Gateway** acts as a central hub, allowing you to connect many VPCs through a single managed service. VPC peering requires a connection between **each pair** of VPCs (full mesh: N(N-1)/2 connections = 4,950 for 100 VPCs). Transit Gateway simplifies this to a hub-and-spoke model — each VPC connects to the gateway, not to each other. VPN CloudHub is for connecting multiple remote sites, not VPCs.

---

## 2. A company needs network traffic to flow between an AWS account in one Region to another account in a different Region. What should they set up between the transit gateways in each region?

### **Answer**

Transit gateway peering attachment.

### **Keywords to remember for MCQ**

- Transit Gateway Peering
- Cross-Region
- Cross-account
- Peering attachment

### **Explanation**

**Transit Gateway Peering** connects two Transit Gateways in different Regions, allowing traffic to flow between VPCs in separate accounts and Regions. PrivateLink is for AWS service access, Site-to-Site VPN is for on-premises to AWS, and Direct Connect is a dedicated physical connection — none of these connect Transit Gateways to each other.

---

## 3. Two VPCs (A: 10.1.0.0/16 and B: 10.2.0.0/16) in the same account. What is the simplest way to connect them?

### **Answer**

VPC peering.

### **Keywords to remember for MCQ**

- VPC Peering
- Same account
- Non-overlapping CIDR
- Simplest solution

### **Explanation**

**VPC Peering** creates a direct network connection between two VPCs using private IP addresses. It's the simplest solution for two VPCs in the same account. VPC endpoints are for AWS service access, Site-to-Site VPN is for on-premises, and Direct Connect is a physical connection — all overkill for connecting two VPCs.

---

## 4. Systems in a secure subnet must access a bucket in Amazon S3. Which solutions stop traffic from crossing the internet? (Select TWO)

### **Answer**

- Create a VPC gateway endpoint for Amazon S3. ✅
- Use VPC interface endpoints. ✅

### **Keywords to remember for MCQ**

- VPC Gateway Endpoint
- VPC Interface Endpoint
- S3 access
- Stay within AWS network
- No internet crossing

### **Explanation**

Both **Gateway** and **Interface VPC endpoints** keep traffic between your VPC and AWS services **within the AWS network**, never crossing the public internet. For S3 specifically, a **Gateway endpoint** is the preferred choice (free, no throughput limits). Interface endpoints are also valid but have hourly charges. VPC peering to S3 is not possible, and S3 doesn't have private IP addresses.

---

## 5. Three VPCs (A, B, C). A and B are peered. B and C are peered. A cannot communicate with C. What is the simplest and most cost-effective way to enable full communication between A and C?

### **Answer**

Add a peering connection between A and C, and route traffic between A and C through the peering connection.

### **Keywords to remember for MCQ**

- VPC Peering
- Transitive routing not supported
- Direct peering needed
- Simplest: add peering

### **Explanation**

**VPC Peering does NOT support transitive routing.** If A peers with B and B peers with C, A and C **cannot** communicate through B — they need a **direct peering connection**. Adding a peering connection between A and C is the simplest and cheapest solution. A transit VPC works but adds complexity and cost.

---

## 6. A secondary data center moved to a temporary facility with internet. Needs a secure VPC connection. Must be operational ASAP. Moving again in 2 weeks. Which option?

### **Answer**

AWS Site-to-Site VPN.

### **Keywords to remember for MCQ**

- Site-to-Site VPN
- Fast setup (minutes to hours)
- Over internet
- Temporary/short-term
- Secure (IPsec)

### **Explanation**

**Site-to-Site VPN** can be set up in **minutes to hours** using existing internet connectivity. It's ideal for temporary or short-term needs. **Direct Connect** takes **weeks to months** to provision a physical connection and is overkill for a 2-week temporary setup. VPC endpoints and VPC peering are not for connecting on-premises to VPCs.

---

## 7. A company wants to efficiently route traffic from their on-premises network to an AWS edge location close to their customer gateway device. What should they use?

### **Answer**

AWS Global Accelerator.

### **Keywords to remember for MCQ**

- Global Accelerator
- Edge locations
- Customer gateway
- Efficient routing
- Anycast IP

### **Explanation**

**AWS Global Accelerator** routes traffic through the **AWS global network** to the nearest edge location, then optimizes the path to your application. It's designed for optimizing traffic to edge locations. VPN CloudHub is for connecting multiple remote sites, Transit Gateway is for VPC-to-VPC, and Direct Connect is a physical connection.

---

## 8. A company wants to back up on-premises systems to AWS. Which network connectivity method provides the most consistent performance?

### **Answer**

AWS Direct Connect.

### **Keywords to remember for MCQ**

- Direct Connect
- Dedicated physical connection
- Consistent performance
- Low latency
- Predictable bandwidth

### **Explanation**

**AWS Direct Connect** provides a **dedicated physical network connection** with consistent bandwidth and latency — ideal for backup workloads that require predictable performance. VPN varies based on internet conditions. VPC endpoints and VPC peering are for AWS-to-AWS connectivity, not on-premises to AWS.

---

## 9. A company uses a single Direct Connect connection. They want to ensure high availability with a backup connection. What is the most cost-effective backup?

### **Answer**

An on-demand AWS Site-to-Site VPN connection across the internet.

### **Keywords to remember for MCQ**

- Backup connection
- Site-to-Site VPN
- Most cost-effective
- Redundancy
- On-demand

### **Explanation**

A **Site-to-Site VPN** is **on-demand** and uses the internet, making it the **most cost-effective** backup option. A second Direct Connect through the same location doesn't provide AZ redundancy. A second Direct Connect through a different location is expensive (physical circuit fees). Client VPN is for individual users, not site-to-site backup.

---

## 10. A company connects a VPC to multiple on-premises data centers using VPN. Which implementation ensures resiliency and predictable bandwidth?

### **Answer**

Implement Direct Connect as the primary connection and use the VPN as a secondary failover connection from each data center.

### **Keywords to remember for MCQ**

- Direct Connect + VPN
- Primary + failover
- Resiliency
- Predictable bandwidth
- Hybrid connectivity

### **Explanation**

**Direct Connect** provides **predictable bandwidth** and low latency as the primary connection. **VPN over internet** serves as a **cost-effective secondary failover** if Direct Connect fails. This combination gives both performance and resiliency. Transit Gateway connects VPCs, not on-premises. VPC peering is AWS-only. Multiple BGP sessions improve routing but don't provide physical redundancy.
