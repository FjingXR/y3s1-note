# Module 10: High Availability & Monitoring — Knowledge Check

---

## 1. Which statement about Amazon EC2 Auto Scaling is accurate?

### **Answer**

It can launch Amazon EC2 instances in multiple Availability Zones.

### **Keywords to remember for MCQ**

- EC2 Auto Scaling
- Multiple Availability Zones
- Launches AND terminates instances
- Not just Reserved Instances
- Can schedule scaling

### **Explanation**

**EC2 Auto Scaling** distributes instances across **multiple Availability Zones** for high availability. It can **launch AND terminate** instances automatically based on policies (not manual). It supports On-Demand, Reserved, and Spot instances — not just Reserved Instances. It also supports scheduled scaling.

---

## 2. A devops engineer detected that demand on EC2 instances increases by a set amount on weekend days. Which scaling type?

### **Answer**

Scheduled.

### **Keywords to remember for MCQ**

- Scheduled scaling
- Known/predictable patterns
- Day of week
- Recurring schedule
- Cron expressions

### **Explanation**

**Scheduled scaling** is ideal when you know traffic follows **predictable, recurring patterns** (like weekend increases). You create a scheduled action that adjusts capacity at specific times. Dynamic scaling reacts to metrics in real-time, predictive scaling uses ML to forecast, and manual scaling requires human intervention.

---

## 3. EC2 instances must maintain 50% average CPU utilization. Which scaling type based on CPU?

### **Answer**

Target tracking scaling.

### **Keywords to remember for MCQ**

- Target tracking
- Maintains target value (e.g., 50% CPU)
- Automatic adjustments
- Simple configuration
- Set-and-forget

### **Explanation**

**Target tracking scaling** lets you set a **target metric value** (like 50% CPU), and Auto Scaling **automatically adjusts** capacity to maintain that target. It's the simplest approach — you define the target, and the system handles everything else. Step scaling requires predefined thresholds, and simple scaling has cooldown periods.

---

## 4. How can a user vertically scale an Amazon RDS database?

### **Answer**

By changing the instance class or size.

### **Keywords to remember for MCQ**

- Vertical scaling RDS
- Change instance class/size
- Larger instance = more CPU/RAM
- Downtime required
- Not horizontal scaling

### **Explanation**

**Vertical scaling** means moving to a **larger instance class** with more CPU and RAM. For RDS, you modify the instance to a bigger type (e.g., db.m5.large → db.m5.xlarge). This requires **downtime** during the change. Sharding, read replicas, and dedicated nodes are **horizontal** scaling approaches.

---

## 5. How can an AWS customer horizontally scale an Amazon Aurora database?

### **Answer**

By adding Aurora Replica instances by using Aurora Auto Scaling.

### **Keywords to remember for MCQ**

- Horizontal scaling Aurora
- Aurora Replica instances
- Aurora Auto Scaling
- Read replicas
- Not changing instance type

### **Explanation**

**Horizontal scaling** for Aurora means adding **more Aurora Replica instances** to distribute read traffic. **Aurora Auto Scaling** automatically adjusts the number of replicas based on read load. Changing the instance type is vertical scaling. CloudWatch alarms and scaling policies are monitoring/configuration tools, not scaling methods.

---

## 6. How does Amazon DynamoDB perform automatic scaling?

### **Answer**

It adjusts the provisioned throughput capacity in response to traffic patterns.

### **Keywords to remember for MCQ**

- DynamoDB auto scaling
- Adjusts provisioned throughput
- Read/write capacity units
- Traffic pattern based
- Not instance type changes

### **Explanation**

**DynamoDB Auto Scaling** automatically adjusts **provisioned read and write capacity** based on traffic patterns. It scales capacity up when demand increases and down when demand decreases, maintaining target utilization. DynamoDB doesn't use instances, read replicas, or instance types — it's a fully managed serverless database.

---

## 7. EC2 instances run an application using TCP port 42000. Client connections from the internet must balance across instances. Which load balancer?

### **Answer**

Network Load Balancer.

### **Keywords to remember for MCQ**

- Network Load Balancer (NLB)
- TCP/UDP protocol
- High performance
- Custom ports
- Millions of requests/sec

### **Explanation**

**Network Load Balancer** operates at **Layer 4 (TCP/UDP)** and can handle custom TCP ports like 42000 with **extremely low latency** and millions of requests per second. Application Load Balancer operates at Layer 7 (HTTP/HTTPS) and is better for HTTP routing. Classic Load Balancer is legacy. Gateway Load Balancer is for third-party virtual appliances.

---

## 8. A company must build a highly available website using server-side scripts for dynamic HTML. Which solution for HIGHEST availability with LEAST cost and complexity?

### **Answer**

An Auto Scaling group launches Amazon EC2 instances, which are served by an Application Load Balancer. DNS name resolution points to the load balancer.

### **Keywords to remember for MCQ**

- ALB + Auto Scaling
- Dynamic HTML (server-side)
- High availability
- Least cost/complexity
- ALB handles HTTP/HTTPS

### **Explanation**

**ALB + Auto Scaling** is the most cost-effective and simple solution for dynamic web content. ALB handles HTTP/HTTPS traffic and distributes it across instances, while Auto Scaling maintains availability. A second Region for DR adds cost and complexity. S3 only hosts static content. NLB doesn't handle HTTP routing.

---

## 9. Users in location A connect to Region A. Users in location B connect to Region B. If Region A becomes unhealthy, traffic for A must redirect to Region B. Which solution?

### **Answer**

Use geolocation routing with failover records in Amazon Route 53.

### **Keywords to remember for MCQ**

- Geolocation routing
- Failover records
- Route 53
- Region failover
- Health checks

### **Explanation**

**Geolocation routing** directs users based on their location to the correct Region. **Failover records** with Route 53 health checks automatically redirect traffic when a Region becomes unhealthy. Latency-based routing chooses the lowest latency but doesn't handle failover. CloudWatch alarms can trigger failover but don't handle routing.

---

## 10. A software engineer wants to stay within the Free Tier and avoid unexpected costs. Which approach with LEAST effort?

### **Answer**

Create an Amazon CloudWatch alarm to send an email message when the account billing exceeds $0.

### **Keywords to remember for MCQ**

- CloudWatch billing alarm
- Free Tier alerts
- Email notification
- Least effort
- Budget threshold

### **Explanation**

A **CloudWatch billing alarm** is the simplest way to get notified when charges exceed a threshold (like $0 for Free Tier). It sends an **email alert** automatically. Checking the console monthly requires manual effort, SCPs are complex to set up, and a CloudWatch metric at $0 is overly restrictive — an alarm with email notification is the least effort approach.
