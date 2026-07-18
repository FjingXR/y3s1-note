# Module 15: Data Processing Pipelines — Knowledge Check

---

## 1. Which scenario describes a challenge to data velocity?

### **Answer**

A shopping website collects clickstream to make personalized recommendations while a user is shopping. When the website is very busy, there is a delay in returning results to customers.

### **Keywords to remember for MCQ**

- Data velocity
- Real-time processing delay
- Clickstream data
- High traffic = delays
- Not data variety or volume

### **Explanation**

**Data velocity** is about the **speed at which data is generated and processed**. The shopping website's delay in returning results during high traffic is a velocity challenge — data arrives faster than it can be processed. Data lineage/quality issues are about data **variety** or **veracity**, and different file formats are a **variety** challenge.

---

## 2. Which statement describes the goal of a modern data architecture?

### **Answer**

Give users the ability to access all of an organization's data by integrating a data lake, a data warehouse, and other purpose-built data stores.

### **Keywords to remember for MCQ**

- Modern data architecture
- Data lake + data warehouse
- Purpose-built data stores
- Integrate multiple stores
- Not a single warehouse only

### **Explanation**

A **modern data architecture** integrates a **data lake** (for raw/unstructured data), a **data warehouse** (for structured analytics), and **purpose-built stores** (like graph DBs, time-series DBs) to give users comprehensive access. It's not just a warehouse, not just streaming, and not a single ingestion service.

---

## 3. Which analytic workload scenario can be a use case for batch ingestion?

### **Answer**

Send sales transaction data from a retailer's website to a central location periodically. Analyze the data overnight, and deliver reports to branches in the morning.

### **Keywords to remember for MCQ**

- Batch ingestion
- Periodic (not real-time)
- Overnight analysis
- Scheduled reports
- Not real-time clickstream or alerts

### **Explanation**

**Batch ingestion** collects data **periodically** (hourly, daily) and processes it in bulk. Overnight analysis with morning reports is the classic batch pattern. Real-time dashboards, continuous clickstream, and immediate fraud alerts require **streaming** ingestion.

---

## 4. RNA sequencing results stored on-premises need to be ingested into AWS. How should they ingest this data?

### **Answer**

Use AWS DataSync to transfer data from the on-premises file store to an Amazon S3 bucket in the data lake.

### **Keywords to remember for MCQ**

- AWS DataSync
- On-premises file store to S3
- Large data transfers
- Not DMS (databases)
- Not Data Exchange (subscriptions)

### **Explanation**

**AWS DataSync** is designed for **large-scale data transfers** from on-premises file systems (NFS, SMB) to AWS storage (S3). DMS is for databases, AppFlow is for SaaS integrations, and Data Exchange is for subscribing to third-party datasets.

---

## 5. A data engineer ingested a new JSON file into S3. Which AWS Glue feature discovers schema with fewest steps code-free?

### **Answer**

Run an AWS Glue crawler on the S3 bucket.

### **Keywords to remember for MCQ**

- AWS Glue crawler
- Schema discovery
- Code-free
- Automatic metadata
- Not Glue Studio or workflows

### **Explanation**

A **Glue crawler** automatically **discovers schema** and populates the **Glue Data Catalog** — it's code-free and requires just a few clicks. Glue Studio is for visual ETL scripting, Glue workflows are for orchestration, and neither discovers schema automatically like a crawler.

---

## 6. Clickstream data must be transformed in real-time for OpenSearch dashboard and generate monthly reports. Which configuration?

### **Answer**

Use Amazon Kinesis Data Streams to capture the data. Use Amazon Managed Service for Apache Flink to consume and transform data from the stream. Use Amazon Data Firehose to deliver transformed data to OpenSearch Service.

### **Keywords to remember for MCQ**

- Kinesis Data Streams → capture
- Managed Flink → transform
- Data Firehose → deliver to OpenSearch
- Real-time + batch reporting
- Not Firehose alone (limited transform)

### **Explanation**

**Kinesis Data Streams** captures streaming data, **Managed Flink** transforms it in real-time, and **Data Firehose** delivers to OpenSearch. This pipeline handles both real-time dashboards and batch storage in S3 for monthly reports. Firehose alone can't do complex transformations.

---

## 7. Which statement accurately describes a consideration for designing pipeline storage?

### **Answer**

Archive data out of relational databases into a more cost-efficient storage option.

### **Keywords to remember for MCQ**

- Pipeline storage design
- Archive to cost-efficient storage
- Not always fastest or cheapest
- Match storage to use case
- Not raw data in warehouse

### **Explanation**

A key storage consideration is **tiering** — archive old data to cheaper storage (like S3 Glacier) to reduce costs. You shouldn't always choose the fastest or cheapest option; you should **match storage to the use case**. Raw data goes in a data lake, not a warehouse.

---

## 8. A data engineer needs a low-cost infrastructure to store structured and unstructured data from a central repository. Which option?

### **Answer**

Amazon S3.

### **Keywords to remember for MCQ**

- Amazon S3
- Central data lake repository
- Structured AND unstructured
- Low-cost storage
- Not databases (structured only)

### **Explanation**

**Amazon S3** is the foundation of a **data lake** — it stores any data type (structured, unstructured, semi-structured) at **low cost** with virtually unlimited scalability. DMS is a migration tool, Redshift is for structured analytics, and QLDB is for ledger data.

---

## 9. A DevOps engineer is migrating an on-premises Apache Hadoop cluster to AWS with scheduled parallel processing jobs. Which service?

### **Answer**

Amazon EMR.

### **Keywords to remember for MCQ**

- Amazon EMR
- Hadoop migration
- Parallel processing
- Big data frameworks
- Not Glue (serverless ETL)

### **Explanation**

**Amazon EMR** is the AWS service for running **Hadoop, Spark, and other big data frameworks** with parallel processing. It's the direct migration path for on-premises Hadoop clusters. Glue is serverless ETL, Glue DataBrew is for data preparation, and Managed Flink is for stream processing.

---

## 10. A marketing manager needs one-time insights on leads and closed deals across postal codes. Most cost-effective query method on S3?

### **Answer**

Amazon Athena.

### **Keywords to remember for MCQ**

- Amazon Athena
- One-time ad-hoc queries
- Serverless SQL on S3
- Pay per query
- Not Redshift (provisioned)

### **Explanation**

**Amazon Athena** is a **serverless, pay-per-query** service for running SQL on S3 data — perfect for **one-time ad-hoc analysis**. Redshift requires provisioning clusters (costly for one-time use), QuickSight is for visualization, and OpenSearch is for log analytics.
