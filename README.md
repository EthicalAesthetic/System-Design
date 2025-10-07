# System Design 30 Concepts

## 1. Client-Server Architecture

- **What?** Every web/app system is built on this classic model.
- **Visual:**
[Client (browser/mobile)] → [Server (backend)]
- **How?**  
Client sends request (store/retrieve/change data) → server processes → sends response.
![Client-Server Architecture](https://substack-post-media.s3.amazonaws.com/public/images/05ba06b8-7730-4d3e-a6d9-1f8c81770b55_1364x446.png)

---

## 2. IP Addresses

- Servers are uniquely located via IP addresses (like phone numbers).
- Without an address, clients can’t contact servers.
![IP Address concept](https://substack-post-media.s3.amazonaws.com/public/images/befd954a-3bf4-4000-9749-8bbe491b7881_1304x848.png)

---

## 3. Domain Name System (DNS)

- We don’t use raw IP addresses — we use domain names (eg. _algomaster.io_).
- **DNS** maps domain names ↔ IP addresses.
- When you visit a site, your computer queries DNS for the real IP.
![DNS Resolution flow](https://substack-post-media.s3.amazonaws.com/public/images/7a22b7b4-f51c-47c7-a9db-abb5ce56def7_1284x916.png)

---

## 4. Proxy / Reverse Proxy

- **Proxy:**  
Middleman between you and internet; hides your IP, adds privacy.
![Proxy Diagram](https://substack-post-media.s3.amazonaws.com/public/images/f11ff886-4db5-4550-aa0f-5f232b094b03_887x477.png)
- **Reverse Proxy:**  
Middleman for servers. Balances or controls traffic going into your backend servers.
![Reverse Proxy Diagram](https://substack-post-media.s3.amazonaws.com/public/images/3be42662-47d2-4165-b278-95d583e2d2be_904x517.png)

### Proxy vs Reverse Proxy
![Proxy vs Reverse Proxy explained](https://substackcdn.com/image/fetch/$s_!dGvk!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F87424c89-0ba3-4580-89bb-ccd5870dff69_945x419.png)
---

## 5. Latency

- **What?** The time it takes data to travel from client to server and back.
- **Why?**  
High if you’re far from server. Reduce by deploying servers closer to users.
![Latency and distance](https://substack-post-media.s3.amazonaws.com/public/images/664e76b6-37fa-4e36-b8a5-d41a5b0ad93a_1866x988.png)
---

## 6. HTTP / HTTPS

- **HTTP:** Request-response protocol for web traffic.
- **HTTPS:** Secures HTTP with SSL/TLS; encrypts data, prevents tampering.
![HTTP Protocol](https://substack-post-media.s3.amazonaws.com/public/images/46796792-f8b5-4e13-b4c2-6920b3d6e0e7_1942x1170.png)
---

## 7. APIs

- Standard way for clients ↔ servers to communicate (abstracts low-level details).
- Typically serve **JSON** or **XML** responses.
![API abstraction](https://substack-post-media.s3.amazonaws.com/public/images/0c3a0e69-9134-4bd9-9d42-a898bc838e32_1574x504.png)

- [What’s an API?](https://blog.algomaster.io/p/whats-an-api)  

---

## 8. REST

- Most popular API style.
- Stateless, relies on HTTP methods: GET, POST, PUT, DELETE.
- Treats everything as a resource (e.g., `/users`, `/orders`).
![REST API style](https://substack-post-media.s3.amazonaws.com/public/images/5c704568-18c9-48e5-ba45-f8e6e1e25a6b_1554x896.png)
---

## 9. GraphQL

- Lets clients request exactly the data they want — nothing more, nothing less.
- Reduces over-fetching, better for complex, nested queries.
- Trade-off: harder to cache, more server processing.
![GraphQL Query and Response](https://substack-post-media.s3.amazonaws.com/public/images/5b40446b-9156-4e7f-9107-654235bb1e53_2138x1806.png)
---
### Rest vs GraphQL
![REST vs GraphQL comparison](https://substackcdn.com/image/fetch/$s_!cEwV!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fc4d86506-cb5f-4c9f-a56a-257439ec46eb_1666x1210.png)
---


## 10. Database

- Backs all apps with reliable data storage and retrieval.
- Apps ask databases to save/return information as needed.
![Database diagram](https://substack-post-media.s3.amazonaws.com/public/images/57b338e3-3cc2-4bcf-86e4-0aa42cc2c2de_1060x884.png)

- [15 Types of Databases](https://blog.algomaster.io/p/15-types-of-databases)
---
---

## 11. SQL vs NoSQL

|                | SQL                    | NoSQL                         |
|----------------|------------------------|-------------------------------|
| Schema         | Fixed, predefined      | Flexible                      |
| Scaling        | Vertically (scale up)  | Horizontally (scale out)      |
| Use case       | Banking, transactions  | Big data, real-time, flexible |
| Examples       | MySQL, Postgres        | MongoDB, Cassandra            |

![SQL vs NoSQL comparison](https://substack-post-media.s3.amazonaws.com/public/images/a81088b7-a188-4089-845a-63936e930a71_1632x1076.png)

- [SQL vs NoSQL - Key Differences](https://blog.algomaster.io/p/sql-vs-nosql-7-key-differences)
---
- **Hybrid** solutions are common.

---

## 12. Vertical Scaling

- Upgrade a single server’s RAM/CPU/disk.
- **Problems:** Expensive; physical limits; single point of failure.
![Vertical Scaling](https://substack-post-media.s3.amazonaws.com/public/images/491fc8b1-02e4-490c-bb5f-87286df10730_1086x556.png)

---

## 13. Horizontal Scaling

- Add more servers, each handling part of the overall load.
- **Advantage:** Better reliability and scalability.
![Horizontal Scaling](https://substack-post-media.s3.amazonaws.com/public/images/c8bba98b-abf7-42de-b699-0de1bcde0454_1180x426.png)

---

## 14. Load Balancer

- Distributes traffic among servers using algorithms (round robin, least connections, etc.)
- If one server fails, the load balancer redirects clients to healthy servers.
![Load Balancer Operation](https://substack-post-media.s3.amazonaws.com/public/images/aebd5461-34f3-47c5-bc8e-5248bb9a92c8_1304x1050.png)
- [Load Balancing Algorithms](https://blog.algomaster.io/p/load-balancing-algorithms-explained-with-code)

---

## 15. Indexing

- Like a book’s index — fast lookups in databases.
- **Trade-off:** Improves reads, but makes writes slower.
- Index only common query columns.
![Indexing visual](https://substack-post-media.s3.amazonaws.com/public/images/e6543930-e7ce-4dda-b4b2-82db93223aa7_1330x788.png)
- [Guide to Database Indexes](https://blog.algomaster.io/p/a-detailed-guide-on-database-indexes)

---

## 16. Replication

- Real-world: Copies of data across multiple servers.
- **Primary** handles writes, **replicas** handle reads.
- Increases fault tolerance and read speed.
![Database Replication](https://substack-post-media.s3.amazonaws.com/public/images/6d8f5734-fd0b-4591-a1a5-082cea0212ce_970x730.png)

---

## 17. Sharding

- **Horizontal partitioning:**  
Split data by ROWS, each “shard” lives on a different server.
- Sharding Key (e.g., userID).
- Good for huge user bases.
![Database Sharding](https://substack-post-media.s3.amazonaws.com/public/images/6e67c3b7-92cd-4f84-854e-e71f45f7efa2_1902x668.png)

- [Database Sharding explained](https://blog.algomaster.io/p/what-is-database-sharding)
---

## 18. Vertical Partitioning

- **Split by COLUMNS**.  
E.g., user profile, login history, billing info = separate tables.
![Vertical Partitioning Example](https://substack-post-media.s3.amazonaws.com/public/images/75daa5e9-2a22-440f-bba3-f1336f613339_2282x1006.png)

---

## 19. Caching

- Store frequently-used data in memory, not DB — makes reads very fast.
- **Cache Aside Pattern:**  
Check cache → if miss, fetch from DB, then update cache.
- **Time-to-Live (TTL):** Expires old cache.
![Cache Aside Pattern](https://substack-post-media.s3.amazonaws.com/public/images/cc5992eb-9290-49c7-ad8d-594a7560ef41_2200x1102.png)
- [Caching Strategies Overview](https://blog.algomaster.io/p/top-5-caching-strategies-explained)

---

## 20. Denormalization

- Combine tables to avoid slow joins (trades storage for speed).
- E.g., merge `user` and `orders` to get user order history fast.
![Denormalization visual](https://substack-post-media.s3.amazonaws.com/public/images/92757591-63fa-4a56-a7cc-e65b739b057a_1750x1398.png)

- **More space, faster reads; harder writes.**

---

## 21. CAP Theorem

- Distributed systems must trade-off between:
- **Consistency** (all nodes see same data)
- **Availability** (every request gets response)
- **Partition tolerance** (system works even if parts can’t talk)
- You can only guarantee **two**.
![CAP Theorem diagram](https://substack-post-media.s3.amazonaws.com/public/images/cd38a5f6-aca6-44e9-aa69-321ed4b04e03_1138x904.png)
- [CAP Theorem Explained](https://blog.algomaster.io/p/cap-theorem-explained)

---

## 22. Blob Storage

- Store large, unstructured files (videos, images, PDFs).
- Use cloud services like Amazon S3, retrieve via URLs.
- Great for streaming/static assets.
![Blob Storage concept](https://substack-post-media.s3.amazonaws.com/public/images/cc338f10-3918-49f5-a828-fced5e905acb_298x306.png)

---

## 23. Content Delivery Network (CDN)

- **Global cache:** Delivers content from nearest server, minimizing latency.
- Used for images, video, static files.
![CDN global servers](https://substack-post-media.s3.amazonaws.com/public/images/a09696e9-f98e-47bd-9eb9-08a20c60464d_5667x2834.png)
- [What is a CDN?](https://www.cloudflare.com/learning/cdn/what-is-a-cdn/)
- [Blog: Content Delivery Networks](https://blog.algomaster.io/p/content-delivery-networks)

---

## 24. WebSockets

- Persistent, bidirectional client-server connection.
- Real-time — suitable for chats, live dashboards.
- **No need for polling!**
![WebSockets Persistent Connection](https://substack-post-media.s3.amazonaws.com/public/images/57a93491-9dae-4a6d-a661-81ff1437c256_1071x969.png)

---

## 25. Webhooks

- Servers notify each other about events.
- Register a “webhook URL”; provider POSTs data when event occurs.
- Reduces wasted polling/API calls.

![Webhook Architecture Diagram](https://www.svix.com/resources/assets/images/webhook-architecture-diagram-6b10973a8a8a3d828cfc529efdeba286.png)

- [Svix](https://www.svix.com/resources/webhook-architecture-diagram/) 
- [System Design Newsletter](https://newsletter.systemdesign.one/p/how-do-webhooks-work)_

---

## 26. Microservices

- System made of small, focused, independent services.
- Each has own DB, deployments; communicate via APIs or message queues.

![Microservices Architecture](https://microservices.io/i/Microservice_Architecture.png)
- [microservices.io](https://microservices.io/patterns/microservices.html) 
- [Multiplayer Microservice Diagrams](https://www.multiplayer.app/distributed-systems-architecture/microservices-diagram/)_

---

## 27. Message Queues

- Allow async, decoupled communication.
- **Producer** puts message in queue; **consumer** processes it later.
- Increases reliability and prevents overload.

![Message Queue Diagram](https://substackcdn.com/image/fetch/$s_!eS0V!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fca06a1be-7aa3-4869-bff1-90a9cfa23630_800x173.png)
- [System Design but Simple - Message Queues](https://www.systemdesignbutsimple.com/p/message-queues-in-1-diagram-and-180-words) 
- [GeeksforGeeks](https://www.geeksforgeeks.org/system-design/message-queues-system-design/)

---

## 28. Rate Limiting

- Restrict number of calls per user/time window.
- Essential to protect against abuse and DoS.
- Use algorithms: fixed/sliding window, token bucket.

- [ByteByteGo](https://bytebytego.com/courses/system-design-interview/design-a-rate-limiter) 
- [GeeksforGeeks Rate Limiting](https://www.geeksforgeeks.org/system-design/rate-limiting-in-system-design/)_

---

## 29. API Gateway

- Single entry point for all APIs in microservice systems.
- Handles:
- Routing
- Authentication
- Rate limiting
- Logging
- Simplifies client code and improves security.

![API Gateway Pattern](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fcb0c8192-4b1b-4834-b068-20d8cfb65050_1856x1412.png)
- [Solo.io](https://www.solo.io/topics/api-gateway/api-gateway-pattern) 
- [GeeksforGeeks API Gateway](https://www.geeksforgeeks.org/system-design/what-is-api-gateway-system-design/)

---

## 30. Idempotency

- Operations have same result no matter how many times executed (e.g., payment process).
- Identify requests with unique IDs; ignore/reject duplicates.
![Idempotency Diagram](https://substackcdn.com/image/fetch/$s_!ydAC!,w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F7b8986fe-7cd6-4e72-b0d6-6ebe49fc29aa_655x536.png)
- [System Design but Simple - Idempotency](https://www.systemdesignbutsimple.com/p/idempotency-in-1-diagram-and-144-words) 
- [GeeksforGeeks Idempotent APIs](https://www.geeksforgeeks.org/system-design/role-of-idempotent-apis-in-modern-systems-design/)_

---

**Author’s Advice:**  
> “Understanding these concepts is the real foundation. Focus on real-world applications, don’t memorize!”  
> **_For in-depth details, check [blog.algomaster.io](https://blog.algomaster.io)_**

---

**_End of Summary_**<br>
[Youtube Video](https://youtu.be/s9Qh9fWeOAk?si=velrRLamAtO9uks1)

**For detailed explanations, deep dives see:**  
- [AlgoMaster System Design Full Guide](https://blog.algomaster.io/p/30-system-design-concepts)  
- [System Design Primer (GitHub)](https://github.com/donnemartin/system-design-primer)  
- [ByteByteGo Visual System Design Patterns](https://bytebytego.com/)

---