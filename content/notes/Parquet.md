---
title: Parquet
tags:
  - DataFundamentals
  - Areas
---
*Open-source columnar storage file format used for big data processing*
- Columnar storage format to allow for optimized column-based operations like filtering/aggregation
- Data in parquet file is divided into columns, and groups of columns are organized into row groups
	- each row group contains a section of data, and group of columns are organized into row groups
	- each row group has some data, and columns within a row group are stored together
- Parquet files contains metadata that define structure of data. The three main metadata that can be found:
	- file metadata - high-level information such as schema, row groups etc.
	- column metadata - encoding, data types, compression etc
	- page-header metadata - data page, dictionary references etc.
- Dictionary encoding: Compresses repetitive data by replacing those values with short id's that refer to a dictionary of unique values
- Predicate pushdown: Query Optimization technique that filters data at source before it's read on memory
	- By applying filtering conditions early in the read process, only relevant data is loaded into memory
Similar to [[ORC]], [[Avro]]

Resource:
- https://learncsdesigns.medium.com/understanding-apache-parquet-d722645cfe74