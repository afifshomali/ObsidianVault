---
tags:
  - CS498DM
---
---
## No SQL
---
![[{898C1E1C-A6DA-4435-AE6C-B0EFAC1BFBA1}.png]]
![[{6CED6FC3-6DB2-431F-BF0B-E234EE705CF5}.png]]

## Key Value Model
---
![[{3FC112A8-FFF3-407C-B980-B6BA47382FEA}.png]]
![[{C7FA8556-B892-4E95-8FAD-3753DF34068A}.png]]
Data Storage:
- values (data) are stored based on the programmer defined keys
	- Keys can be defined in any way the programmer likes
- System is agnostic as to the structure (semantics) of the value
- Queries are expressed in terms of keys
- Indexes are defined over keys (typically primary only)

### Amazon DynamoDB
---
![[{D67D36A4-84C3-4F4B-ACA3-8B9A35A804CC}.png]]
### Riak
---
![[{36F83C9E-8725-436A-B839-6FA7194CB85E}.png]]


## Document Data Model 
---
![[{238E469F-43B6-4408-9CE7-7C9917DE71D1}.png]]
![[{5CFBAAD2-65A4-4A75-987F-6DE84CD5CBE5}.png]]
![[{AA1CFF10-9072-4103-97E2-DD8AF91F5E36}.png]]

Data Storage
- Documents (data) is stored based on programmer defined keys
- System is aware of the arbitrary document structure
- support for lists and nested documents
Queries are expressed in terms of key (or attributes, if index exists)
Support for Key based indexes & secondary indexes 

- They are more complex than key value stores
- Schema: Collection (group of document) + Attributes (attr)
- What is a document?
	- Can store Microsoft word documents but more general than that
	- Document usually means pointer less object with structure
- Usually support secondary indices
- Usually multiple types of documents per database
- Usually nested documents
- No ACID transactions across documents but this has changed recently
- SimpleDB, CouchDB, MongoDB
### Apache CouchDB
---
![[{A770E042-4AD8-4BBC-855D-8C54AC5F47F0}.png]]
![[{21C11528-799B-48D2-8004-1DC195F71D41}.png]]

### MongoDB
---
![[{59AB7253-D5DE-4427-A32F-E61437C52F64}.png]]
