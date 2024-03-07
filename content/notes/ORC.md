---
title: ORC
tags:
  - DataFundamentals
  - Areas
---
*Optimized Row Columnar Format, organized into columns that optimize read/write operations for Apache Hive*
- Apache Hive: data warehouse that has fast data summarization and querying over large datasets
- Columnar storage format to allow for optimized column-based operations like filtering/aggregation
- ORC stores data in a series of stripes where each strip is a collection of rows. 
	- each stripe is further divided into a series of data chunks where each stores data for columns
	- also, metadata can be used to quickly read data without scanning entire file
	- ORC can store indexes for specific columns, for faster retrieval of specific rows

Similar to [[Parquet]], [[Avro]]