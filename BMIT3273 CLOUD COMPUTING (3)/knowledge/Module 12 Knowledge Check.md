# Module 12: Caching Content — Knowledge Check

---

## 1. What is caching?

### **Answer**

A high-speed data storage layer.

### **Keywords to remember for MCQ**

- Caching
- High-speed storage layer
- Faster data access
- Reduces database load
- In-memory storage

### **Explanation**

**Caching** is a **high-speed data storage layer** that stores frequently accessed data in memory for faster retrieval. It sits between the application and the primary data store, reducing latency and load on the backend. It's not a password store, not an in-memory database itself, and not a content delivery network.

---

## 2. Which type of data should you cache?

### **Answer**

Static data that is frequently accessed.

### **Keywords to remember for MCQ**

- Cache static data
- Frequently accessed
- Does not change often
- Product catalogs, images
- Not dynamic/user-specific

### **Explanation**

**Static, frequently accessed data** is ideal for caching because the cached copy stays valid longer. Dynamic content (like user-specific data) changes often and would cause frequent cache invalidation. Data that changes per user or per request isn't a good caching candidate.

---

## 3. Which is a benefit of caching?

### **Answer**

Reduced response latency.

### **Keywords to remember for MCQ**

- Caching benefit
- Reduced latency
- Faster response times
- Lower database load
- Not cost reduction

### **Explanation**

The primary benefit of caching is **reduced response latency** — data is served from fast in-memory storage instead of hitting the database. It also reduces database load and can improve reliability, but the most direct benefit is speed.

---

## 4. Which types of content on a web page can be cached using an edge cache? (Select TWO)

### **Answer**

- Web objects, such as hyperlinks. ✅
- Video files, such as a product demo. ✅

### **Keywords to remember for MCQ**

- Edge cache
- Static web objects
- Video files
- Images, CSS, JS
- Not user-specific data

### **Explanation**

**Edge caches** (like CloudFront) cache **static content** — web objects (images, CSS, JavaScript, hyperlinks) and media files (videos). User-specific data like shopping carts and search terms are dynamic and shouldn't be cached. Dynamically generated content varies per user and isn't suitable for edge caching.

---

## 5. What does Amazon CloudFront enable?

### **Answer**

Multi-tiered and regional caching of content.

### **Keywords to remember for MCQ**

- CloudFront
- Multi-tiered caching
- Regional caching
- Edge locations + Regional Edge Caches
- Content delivery

### **Explanation**

**Amazon CloudFront** provides **multi-tiered caching** with edge locations (closest to users) and **Regional Edge Caches** (larger caches between edge locations and origins). This layered approach maximizes cache hit rates and reduces latency globally.

---

## 6. How does Amazon CloudFront use edge locations?

### **Answer**

It caches frequently accessed content at edge locations. It delivers the cached content to clients through the edge location with the lowest latency to those clients.

### **Keywords to remember for MCQ**

- CloudFront edge locations
- Lowest latency delivery
- Frequently accessed content
- Cache at edge
- Not all content cached at every edge

### **Explanation**

CloudFront caches **frequently accessed content** at **edge locations** closest to users. When a user requests content, CloudFront serves it from the **edge location with the lowest latency** to that user. It doesn't cache all content at every edge, and it doesn't rely on network hops as the routing metric.

---

## 7. Which statement describes an efficient way to deliver on-demand video content?

### **Answer**

Use Amazon S3 to store the content. Then use Amazon CloudFront to deliver the content.

### **Keywords to remember for MCQ**

- Video delivery
- S3 for storage
- CloudFront for delivery
- Cost-effective
- Scalable

### **Explanation**

**S3 + CloudFront** is the most efficient architecture: S3 provides **durable, scalable storage** and CloudFront delivers content through **edge locations** for low latency. Using EC2 to serve video is more expensive and less scalable. Serving directly from S3 without CloudFront means higher latency for distant users.

---

## 8. Which role does Amazon CloudFront play in protecting against DDoS attacks?

### **Answer**

Routes traffic through edge locations.

### **Keywords to remember for MCQ**

- CloudFront DDoS protection
- Edge location routing
- Absorbs attack traffic
- Distributes across edge network
- Not deep packet inspection

### **Explanation**

CloudFront **absorbs and distributes DDoS attack traffic** across its global network of edge locations, preventing traffic from overwhelming your origin. It doesn't perform deep packet inspection, block by source IP, or restrict by geography as its primary DDoS mechanism.

---

## 9. How can an application use Amazon ElastiCache to improve database read performance? (Select TWO)

### **Answer**

- Write data to ElastiCache whenever the application writes to the database. ✅
- Read data from ElastiCache first, and write to ElastiCache when a cache miss occurs. ✅

### **Keywords to remember for MCQ**

- ElastiCache + database
- Write-through caching
- Read from cache first
- Cache miss → write to cache
- Reduces database reads

### **Explanation**

**Write-through caching** writes to both cache and database simultaneously, keeping cache fresh. **Lazy loading** reads from cache first; on a cache miss, it reads from DB and populates the cache. Both strategies reduce database load and improve read performance.

---

## 10. Which caching strategy should be used when there's data that must be updated in real time?

### **Answer**

Write-through.

### **Keywords to remember for MCQ**

- Write-through caching
- Real-time updates
- Cache always fresh
- Write to cache + database together
- Not TTL or lazy loading

### **Explanation**

**Write-through caching** updates the cache and database **simultaneously**, ensuring the cache always has fresh data — critical for real-time requirements. TTL causes stale data until expiration. Lazy loading can serve stale data. Write-through guarantees consistency at the cost of slightly higher write latency.
