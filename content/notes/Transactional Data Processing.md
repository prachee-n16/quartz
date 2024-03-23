---
title: Transactional Data Processing
tags:
  - Databases
  - to-complete
  - Programming
  - Areas
---
*Record transactions that capture business events a company wants to track*

Think of financial transactions: a bank would capture when money is deposited or taken out. Each transaction is a small, discrete unit of work. In the case of a bank, they would be dealing with millions of transactions on a daily basis. 
- The work performed by transactional systems is called **Online Transactional Processing** (OLTP)
	- OLTP rely on [[notes/Databases|database]] systems where storage is optimized for read/write operations. So, it can support multiple CRUD operations while ensuring data is correct
	- OLTP enforces [[notes/Database Transactions|ACID]], typically support live applications that process business data (LOB applications)
