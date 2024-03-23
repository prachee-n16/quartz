---
title: Database Transactions
tags:
  - Databases
  - DataFundamentals
  - Areas
---
**ACID and BASE: Database Transactions**
Following a chemistry analogy, we can measure a pH of a database where:
- ACID databases is for applications that need consistency and reliability
- BASE databases is for applications that need availability, flexibility and scalability

ACID is an acronym that refers to 4 properties a transaction should uphold for reliability of data: Atomicity, Consistency, Isolation, Durability

- Atomicity refers to the entire transaction taking place at once or doesn't happen at all. 
	- Important when processing financial transactions, since if anything goes wrong, we would want to rollback rather than leaving an undesired state
- Consistency refers to the database remaining consistent before and after the transaction.
	- Transactions should ensure consistency with the database's business rules
- Isolation refers to multiple transactions occur independently without interference. 
	- When there are two transactions accessing same data, each occurs either before or after another. 
- Durability refers to the changes of a successful transaction occurs even if the system failure occurs. 
	- Once a transaction is committed to a database, it is permanently remembered through transaction logs. When there is a failure, it can be used to restore transactions.

For NoSQL databases, this is overkill. In fact, the CAP theorem or Brewer's theorem states that any distributed system or data store has two of the three aspects:
- Consistency - does a system reliable follow the rules of the database? do all users see the right data they are supposed to? is it ever in a stale state?
- Availability - is the system available when requested? 
- Partition Tolerance - does a system operate even when there is data loss or system failure?

It's better to use BASE principles:
- Basic Availability focuses on keeping data available even with multiple failures. Instead of having a single large data store, NoSQL skips across many databases with replication. So, some errors does not result in complete outage. 
- Soft state works against consistency where keeping data consistent is the problem of the developer, not database
- Eventual Consistency states that eventually, the database needs to become into a consistent state. 

