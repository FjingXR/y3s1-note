# Module 14: Serverless Computing — Knowledge Check

---

## 1. Which serverless computing benefits should be included in a microservice architecture proposal? (Select THREE)

### **Answer**

- Pay-for-value services. ✅
- Continuous scaling. ✅
- Built-in high availability. ✅

### **Keywords to remember for MCQ**

- Serverless benefits
- Pay-for-value (no idle costs)
- Continuous scaling (auto)
- Built-in high availability
- No full control over runtime

### **Explanation**

Serverless computing offers **pay-for-value** (pay only when code runs), **continuous scaling** (automatic), and **built-in HA** (AWS manages availability). You don't have full control over the runtime environment, performance isn't always predictable (cold starts), and server maintenance is reduced but not eliminated.

---

## 2. A developer needs a simple web form for employee commute info. Which is a serverless solution?

### **Answer**

Host static assets in an Amazon S3 bucket, use an Amazon DynamoDB table, and use Amazon API Gateway and AWS Lambda functions to interact with the database.

### **Keywords to remember for MCQ**

- Serverless web form
- S3 (static assets)
- DynamoDB (database)
- API Gateway + Lambda (backend)
- No EC2, no RDS

### **Explanation**

This is the classic **serverless stack**: **S3** hosts static content, **DynamoDB** stores data, **Lambda** processes requests, and **API Gateway** exposes the HTTP API. No servers to manage. ECS with Fargate isn't fully serverless (still container management), and RDS isn't serverless (requires instance management).

---

## 3. Why would a solutions architect recommend a microservice architecture? (Select TWO)

### **Answer**

- Independent from other components. ✅
- Solves a specific business problem. ✅

### **Keywords to remember for MCQ**

- Microservices benefits
- Independent components
- Specific business problem
- Single responsibility
- Not about interfaces or protocols

### **Explanation**

Microservices are **independent** (one service can fail without breaking others) and each **solves a specific business problem** (single responsibility). They don't inherently provide industry-standard interfaces, HTTP(S) communication, or open-source code.

---

## 4. Which scaling configuration is needed for Lambda function scaling?

### **Answer**

None because the AWS Lambda service scales functions automatically.

### **Keywords to remember for MCQ**

- Lambda scaling
- Automatic (no configuration)
- Scales per request
- No Auto Scaling groups
- No manual provisioning

### **Explanation**

**Lambda scales automatically** — AWS provisions new instances in response to incoming requests with no configuration needed. There are no Auto Scaling groups, no manual capacity planning, and no auto scaling parameter to configure. Lambda handles it all.

---

## 5. A solutions architect needs to use a custom library in Lambda functions. Which feature?

### **Answer**

Lambda layers.

### **Keywords to remember for MCQ**

- Lambda layers
- Shared custom libraries
- Package code + dependencies separately
- Reuse across functions
- Not triggers or destinations

### **Explanation**

**Lambda layers** let you package **custom libraries and dependencies** separately from your function code. Multiple functions can share the same layer, reducing deployment package size and simplifying updates. Destinations handle async results, triggers are event sources, and function URLs are HTTP endpoints.

---

## 6. Which statements are true for software packaged as a container?

### **Answer**

Standardized, portable application code packages that contain code and code dependencies. A container is run by a container engine. A container does not include a guest operating system.

### **Keywords to remember for MCQ**

- Container characteristics
- Standardized, portable
- Code + dependencies
- Run by container engine (not hypervisor)
- No guest OS

### **Explanation**

Containers are **standardized, portable packages** containing code and dependencies. They run on a **container engine** (like Docker), not a hypervisor. Unlike VMs, containers **don't include a guest OS** — they share the host OS kernel, making them lightweight and fast to start.

---

## 7. Which is the most effective container deployment when refactoring a monolith to microservices on ECS?

### **Answer**

Create services that each provide a distinct function of the application, and run each service in a separate container that Amazon ECS manages.

### **Keywords to remember for MCQ**

- ECS microservices
- Separate container per function
- Each service = one container
- Single responsibility
- Not multiple services in one container

### **Explanation**

The most effective approach is **one container per distinct function** — each microservice runs in its own ECS-managed container. This provides independence, scalability, and fault isolation. Putting multiple services in one container defeats the purpose of microservices. Just porting the monolith to a container doesn't achieve microservices.

---

## 8. Sensor data in DynamoDB needs HTTPS read-only access. Intermittent usage (68% idle). Which solution most cost-efficient and secure?

### **Answer**

Create a public interface by using Amazon API Gateway with Lambda functions accessing the DynamoDB sensor database.

### **Keywords to remember for MCQ**

- API Gateway + Lambda
- Intermittent usage (pay-per-use)
- Serverless = most cost-efficient
- HTTPS built-in
- No idle EC2 costs

### **Explanation**

**API Gateway + Lambda** is perfect for **intermittent workloads** — you pay only when requests come in (68% idle time = zero idle cost). HTTPS is built-in, and Lambda requires no operational maintenance. ECS with EC2 has idle costs, direct DynamoDB access isn't secure for public users, and web proxies on EC2 are expensive and complex.

---

## 9. Which workflows are suitable for AWS Step Functions? (Select THREE)

### **Answer**

- Update inventory and run a shipment workflow when a customer purchases an item on an e-commerce site. ✅
- Coordinate multi-step analytics and machine learning workflows. ✅
- Implement manual approval in a security incident response workflow. ✅

### **Keywords to remember for MCQ**

- Step Functions use cases
- Multi-step workflows
- Manual approval steps
- ML/analytics orchestration
- Not for simple notifications or single EC2 tasks

### **Explanation**

Step Functions excel at **multi-step workflows** (e-commerce order processing), **ML/analytics pipelines** (coordinating multiple services), and **manual approval steps** (security incident response). They're overkill for simple S3 notifications or deploying based on environment variables.

---

## 10. A developer wants to implement a manual approval step in Step Functions. Which should be implemented?

### **Answer**

A task or activity state with an activated wait for callback parameter.

### **Keywords to remember for MCQ**

- Step Functions manual approval
- Task/activity state
- Wait for callback
- Pauses until approval/rejection
- Not map state

### **Explanation**

A **task or activity state** with **wait for callback** pauses the state machine until an external process (like an approval email) sends a callback signal. Map states are for parallel iterations, not approval workflows. The state pauses and resumes when the callback is received.
