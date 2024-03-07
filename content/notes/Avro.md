---
title: Avro
tags:
  - DataFundamentals
---
- Each record has a header that describes the structure of data it contains
	- Data is stored as binary information, and information in header is used to parse data and extract fields
	- Good format for compressing data, minimize storage and network bandwidth requirements

**Evolution of data formats to Avro:**
With [[notes/Delimited Text Files|Delimited Text Files]], there are some disadvantages:
- Data types need to be inferred, and not a guarantee
- Parsing is tricky if data has commas
- Column names might not be there

[[Relational Databases|Relational Databases]]: add types (fixing the first disadvantage):
```
CREATE TABLE fruits {
	id      integer PRIMARY KEY,
	name    varchar(20)
}
```
However, this data is flat i.e. stored in plain text format and this data is stored in databases, where this definition might be different across databases.

[[JSON]]: a widely accepted format that can take any form and easily shared over network. 
- Still, there's no type definitions. 
- Repeated keys leads to bigger JSON objects
- No comments, metadata, documentation

With Avro, the advantages are:
- Data is fully typed, schema is defined, and compressed automatically
- Documentation is embedded into schema
- Safe schema evolution

Similar to [[Parquet]], [[ORC]]