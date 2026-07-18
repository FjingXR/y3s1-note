# Module 16: Disaster Recovery — Knowledge Check

---

## 1. What are the definitions for recovery point objective (RPO) and recovery time objective (RTO)?

### **Answer**

RPO is the maximum acceptable data loss, measured in time. RTO is the maximum acceptable time until recovery.

### **Keywords to remember for MCQ**

- RPO = max data loss (time)
- RTO = max downtime (time)
- Both measured in time (not bytes)
- Not average recovery time
- Critical DR metrics

### **Explanation**

**RPO** defines the **maximum acceptable data loss** — how far back in time you can afford to lose (e.g., RPO = 1 hour means you can lose up to 1 hour of data). **RTO** defines the **maximum acceptable downtime** — how long you can afford to be offline (e.g., RTO = 4 hours means recovery must complete within 4 hours).

---

## 2. What can you do to quickly replicate or redeploy environments in a disaster?

### **Answer**

Use AWS CloudFormation templates to deploy duplicate environments in the same Region.

### **Keywords to remember for MCQ**

- CloudFormation templates
- Quick environment redeployment
- Duplicate environments
- Infrastructure as Code
- Not Elastic Beanstalk for VPC deployment

### **Explanation**

**CloudFormation templates** let you rapidly deploy **identical environments** from code — critical for disaster recovery. You can deploy the same stack in the same or different Region in minutes. Elastic Beanstalk deploys apps, not VPCs. OpsWorks is for configuration management, and CodeBuild is for building code.

---

## 3. S3 bucket needs all new and existing objects copied to another Region for DR. Most efficient solution?

### **Answer**

Enable cross-Region replication on the bucket and copy existing objects onto themselves.

### **Keywords to remember for MCQ**

- Cross-Region Replication (CRR)
- Existing + new objects
- Copy existing objects to trigger replication
- Automatic for new objects
- Not Step Functions (manual orchestration)

### **Explanation**

**Cross-Region Replication (CRR)** automatically replicates **new objects** to a destination bucket. To replicate **existing objects**, you copy them onto themselves (which triggers replication). This is the most efficient approach. Lambda-based solutions add complexity, and writing to both buckets manually is error-prone.

---

## 4. Which strategy is the most efficient for Amazon EC2 disaster recovery?

### **Answer**

Store essential data separately from the instance, and develop rapid rebuild processes for compute instances.

### **Keywords to remember for MCQ**

- EC2 DR strategy
- Separate data from compute
- Rapid rebuild processes
- AMIs for quick launch
- Not continuous synchronization

### **Explanation**

The most efficient EC2 DR strategy **decouples data from compute** (store data in S3/EBS) and uses **AMIs/scripts for rapid rebuild**. You don't need to continuously synchronize standby instances (expensive). Regular backups are slow for recovery. Marketplace AMIs add unnecessary cost.

---

## 5. Which service provides automatic failover between multiple endpoints in support of a geographic DR strategy?

### **Answer**

Amazon Route 53.

### **Keywords to remember for MCQ**

- Route 53
- Automatic failover
- Health checks
- Geographic DR
- Not VPC, ELB, or Direct Connect

### **Explanation**

**Amazon Route 53** provides **automatic failover** using **health checks** — when an endpoint becomes unhealthy, Route 53 redirects traffic to a healthy endpoint in another Region. VPC is networking, ELB distributes traffic within a Region, and Direct Connect is a physical connection.

---

## 6. Which statement about the backup and restore DR pattern is true?

### **Answer**

Most cost-effective, but highest recovery time objective (RTO).

### **Keywords to remember for MCQ**

- Backup and restore
- Most cost-effective
- Highest RTO
- Slowest recovery
- Simplest DR pattern

### **Explanation**

**Backup and restore** is the **cheapest DR pattern** — you only pay for backup storage. However, it has the **highest RTO** because you must provision infrastructure, restore data, and bring everything online during a disaster. It also has high RPO (data loss since last backup).

---

## 7. Which statements accurately describe infrastructure characteristics of common DR patterns? (Select TWO)

### **Answer**

- Warm standby has a scaled-down version of all infrastructure that scales as necessary and within pre-defined limits to meet the load when a disaster occurs. ✅
- Pilot light has minimal infrastructure that always runs. The rest of the infrastructure does not run until a disaster occurs. ✅

### **Keywords to remember for MCQ**

- Warm standby = scaled-down always running
- Pilot light = minimal always running
- Warm standby scales up on disaster
- Pilot light starts remaining infra on disaster
- Not full infrastructure always running

### **Explanation**

**Warm standby** runs a **scaled-down version** of all infrastructure that **scales up** during a disaster. **Pilot light** keeps only **minimal critical components** running (like a database), and starts the rest (like EC2 instances) when needed. A second fully functional set running all the time is the **multi-site** pattern.

---

## 8. What does the multi-site DR pattern involve?

### **Answer**

It involves automatic failover to a second fully functional, constantly operational system that is in another site.

### **Keywords to remember for MCQ**

- Multi-site DR
- Two fully functional sites
- Both always operational
- Automatic failover
- Most expensive DR pattern

### **Explanation**

**Multi-site DR** has **two or more fully functional, identical systems** running simultaneously in different locations. Traffic automatically fails over to a healthy site during a disaster. It's the **most expensive** pattern but provides the lowest RPO and RTO.

---

## 9. DR solution for business-critical app needs RTO and RPO in minutes, but don't want to overpay. Which pattern?

### **Answer**

Warm standby.

### **Keywords to remember for MCQ**

- Warm standby
- RTO/RPO in minutes
- Cost-effective for minutes
- Scaled-down infrastructure
- Not multi-site (overpaying)

### **Explanation**

**Warm standby** provides **RTO/RPO in minutes** at a fraction of multi-site cost. You keep a scaled-down version running and scale up during disasters. Backup and restore is too slow (hours). Pilot light may take longer to start all components. Multi-site is overkill if you don't need near-zero RTO/RPO.

---

## 10. What does an AWS Storage Gateway enable you to do? (Select THREE)

### **Answer**

- Transfer backup jobs from tape or Virtual Tape Library (VTL) systems to the cloud. ✅
- Present cloud-based internet Small Computer Systems Interface (iSCSI) block storage volumes to on-premises applications. ✅
- Use Server Message Block (SMB) or Network File System (NFS) to connect to Amazon S3. ✅

### **Keywords to remember for MCQ**

- Storage Gateway
- Tape backup to cloud (VTL)
- iSCSI block volumes to on-prem
- SMB/NFS access to S3
- Hybrid cloud storage

### **Explanation**

**Storage Gateway** provides **hybrid cloud storage** — it connects on-premises apps to AWS storage via **VTL** (tape backups to cloud), **iSCSI** (block volumes), and **SMB/NFS** (file access to S3). It doesn't provide a fully managed NFS endpoint (that's EFS) or API access to S3 (that's direct S3 API).
