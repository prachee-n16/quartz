---
title: Data Stores
tags:
  - DataFundamentals
  - Areas
---
There are two broad categories of data store:
- file stores
- databases
# File Stores
*Store data in files*

The file format used to store data depends on:
1. [[notes/Data Formats|Type of data to be stored]]
2. Application/Services that need to interact (i.e. perform CRUD operations) with data
3. Purpose of storage: Does this need to be readable by humans, or optimized for efficient storage and processing
## Common File Formats
- [[Delimited Text Files]]
- [[JSON]]
- [[XML]]
- [[BLOB]]
- [[Avro]]
- [[ORC]]
- [[Parquet]]
# Databases
*Central system where data is stored and searched through*
- [[Relational Databases]]
- [[Non-relational Databases]]