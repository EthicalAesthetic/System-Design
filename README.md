# System-Design Overview
System design is the process of defining the architecture, interfaces, and data for a system that satisfies specific requirements. System design meets the needs of your business or organization through coherent and efficient systems. It requires a systematic approach to building and engineering systems. A good system design requires us to think about everything, from infrastructure all the way down to the data and how it's stored.

Objective :-
-
- Try to break the problem into simpler modules (Top down approach).
- Talk about the trade-offs (No solution is perfect. Calculate the impact on system baased on all the constraints and the end test cases.)

Learning Objectives
-

<p align="center">
    <img src="Resources/Screenshot%202025-09-30%20122654.png" alt="System Design Screenshot" width="90%">
</p>

## Table of Contens
1. [Load Balancing](#load-balancing)
2. [SQL vs NoSQL](#sql-vs-nosql)

# Load Balancing 
Distrubution of Load on server
## Types of distribution 
- Random 
- Round Robin
- Random (weights for memory and CPU cycles)

![](Resources/Screenshot%202025-09-30%20124848.png)

## Types of Load Balancer
- Hardware 
- Software 
- Hybrid (HA proxy)

![](Resources/Screenshot%202025-09-30%20125332.png)

# SQL vs NoSQL

![](Resources/Screenshot%202025-09-30%20130633.png)

![](Resources/Screenshot%202025-09-30%20130039.png)

We will focus more on <b>Non-relational DB</b> as these are more <b>scalable</b>.

![](Resources/Screenshot%202025-09-30%20130255.png)


Key-value Store -
- Helm charts
- yaml
- Python Dictionary
- BlockChain
- Bitcoin
- Twitter (redis)


Document DB-

- IBM (couchDB) 
- Adobe (MongoDB)


Wide-Column DB-
 
- Discord, Netflix, Uber (Cassandra)


Graph DB- 

- Neo 4J (when grown)


Time Series DB-
- Prometheus (monitoring)
<hr><br>

![](Resources/Screenshot%202025-09-30%20133000.png)







### More to go 

- Monitoring/ observability (Time series DB) (Prometheus)(**must do**)
- ACID 
- Redis
- Defination of Open-Source in INDIA.
