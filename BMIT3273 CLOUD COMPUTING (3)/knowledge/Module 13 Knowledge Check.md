# Module 13: Microservices Architecture — Knowledge Check

---

## 1. Which statement describes the difference between tightly and loosely coupled architectures?

### **Answer**

Components in a tightly coupled architecture are highly dependent on each other. In a loosely coupled architecture, components aren't highly dependent on each other.

### **Keywords to remember for MCQ**

- Tightly coupled = high dependency
- Loosely coupled = low dependency
- Loose coupling = easier scaling
- Tight coupling = more failure risk
- Independence

### **Explanation**

In **tightly coupled** architectures, components are **highly dependent** — a failure in one can cascade to others. **Loosely coupled** components operate independently, making the system more resilient and easier to scale. Loose coupling doesn't require managed services and doesn't necessarily increase scaling complexity.

---

## 2. Which statements describe Amazon Simple Queue Service (Amazon SQS)? (Select THREE)

### **Answer**

- Requires a consumer to poll the queue for messages. ✅
- Stores and optionally encrypts messages until they are processed and deleted. ✅
- Enables you to decouple and scale microservices, distributed systems, and serverless applications. ✅

### **Keywords to remember for MCQ**

- Amazon SQS
- Pull-based (consumer polls)
- Stores messages
- Decouples microservices
- Not push notifications

### **Explanation**

**Amazon SQS** is a **pull-based** message queue — consumers **poll** for messages. It **stores messages** (optionally encrypted) until processed and deleted. It **decouples** components for scalability. SQS doesn't push notifications (that's SNS), doesn't support email/SMS, and standard queues don't have topics.

---

## 3. Which statements are true when using an Amazon SQS standard queue? (Select TWO)

### **Answer**

- Messages can be sent in any order. ✅
- A message might be delivered more than once. ✅

### **Keywords to remember for MCQ**

- SQS Standard queue
- Best-effort ordering (any order)
- At-least-once delivery
- Not FIFO
- Not priority messages

### **Explanation**

**Standard queues** provide **best-effort ordering** (messages can arrive in any order) and **at-least-once delivery** (a message may be delivered multiple times). FIFO queues guarantee order and exactly-once processing. Standard queues don't support message priority.

---

## 4. A fleet of EC2 instances processes uploaded videos. Which SQS function fits this application?

### **Answer**

The application places job messages in an SQS queue. EC2 instances with available processing capacity pull the next job message from the queue.

### **Keywords to remember for MCQ**

- SQS job queue
- Pull-based processing
- EC2 instances poll queue
- Decoupled video processing
- Load balancing across workers

### **Explanation**

SQS acts as a **job queue** — the application publishes job messages, and EC2 instances **pull messages** when they have capacity. This decouples producers from consumers and naturally load balances work. SQS doesn't store video files directly and doesn't push notifications to all instances.

---

## 5. What is Amazon Simple Notification Service (Amazon SNS)?

### **Answer**

A fully managed messaging service for both system-to-system and application-to-person (A2P) communication, which uses publish/subscribe patterns.

### **Keywords to remember for MCQ**

- Amazon SNS
- Publish/subscribe (pub/sub)
- System-to-system AND A2P
- Fully managed
- Fan-out messaging

### **Explanation**

**Amazon SNS** is a **pub/sub messaging service** supporting both **system-to-system** (e.g., S3 → Lambda) and **application-to-person** (e.g., SMS, email, push notifications) communication. It's not just an email service, not a marketing platform, and not an event bus (that's EventBridge).

---

## 6. What are some use cases for Amazon SNS? (Select THREE)

### **Answer**

- Trigger a single AWS Lambda function when an object is created in an Amazon S3 bucket. ✅
- Notify multiple systems that user input is ready for processing. ✅
- Send a text message to systems operators when unusual activity has been detected. ✅

### **Keywords to remember for MCQ**

- SNS use cases
- Trigger Lambda from S3
- Fan-out to multiple systems
- Alert operators (SMS)
- Not for ordered processing

### **Explanation**

SNS is ideal for **event-driven triggers** (S3 → Lambda), **fan-out notifications** (multiple subscribers), and **operator alerts** (SMS for unusual activity). It's not for ordered message processing (that's SQS), not for gathering streaming data, and not for holding input in order.

---

## 7. What are some features of Amazon SNS? (Select TWO)

### **Answer**

- Message delivery to an Amazon SQS queue. ✅
- Message delivery to a URL. ✅

### **Keywords to remember for MCQ**

- SNS features
- Delivery to SQS queue (SQS subscription)
- Delivery to URL (HTTP/S webhook)
- No guaranteed delivery if endpoint inaccessible
- No message recall

### **Explanation**

SNS can **deliver messages to SQS queues** (integrating pub/sub with queuing) and to **URLs via HTTP/S** (webhooks). It doesn't guarantee delivery if the endpoint is unavailable, doesn't support strict ordering with standard topics, and doesn't allow message recall.

---

## 8. Two Lambda functions must process PDFs from S3. S3 event allows only one action. Which solution?

### **Answer**

Send the S3 event to an Amazon SNS topic that both Lambda functions subscribe to.

### **Keywords to remember for MCQ**

- SNS fan-out pattern
- One event → multiple subscribers
- S3 → SNS → 2 Lambda functions
- Least complex solution
- Not SQS (pull-based, not fan-out)

### **Explanation**

**SNS fan-out** is the simplest solution — one S3 event publishes to an SNS topic, and **both Lambda functions subscribe** to it. SQS is pull-based (one consumer gets each message), Amazon MQ adds complexity, and uploading two copies wastes storage.

---

## 9. What is Amazon MQ?

### **Answer**

Message broker service.

### **Keywords to remember for MCQ**

- Amazon MQ
- Message broker
- Apache ActiveMQ / RabbitMQ
- Lift-and-shift from on-premises
- Not identity, migration, or monitoring

### **Explanation**

**Amazon MQ** is a **managed message broker** service supporting **Apache ActiveMQ** and **RabbitMQ**. It's designed for **lift-and-shift** migrations from on-premises message brokers. It's not an identity broker, data migration service, or application monitoring tool.

---

## 10. Which is a common use case for Amazon MQ?

### **Answer**

Leverage an existing on-premises application that uses Apache ActiveMQ to communicate between microservices.

### **Keywords to remember for MCQ**

- Amazon MQ use case
- Lift-and-shift ActiveMQ
- Existing on-premises apps
- Not for new cloud-native apps
- Not for static websites or VPNs

### **Explanation**

Amazon MQ is ideal for **migrating existing on-premises applications** that already use **Apache ActiveMQ** or RabbitMQ to AWS without rewriting messaging code. For new cloud-native applications, SQS or SNS are preferred. Amazon MQ isn't for static websites, VPC connectivity, or decoupling new architectures.
