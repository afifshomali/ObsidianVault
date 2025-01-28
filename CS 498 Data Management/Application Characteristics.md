---
tags:
  - CS498DM
---
---
## Aspects of Applications that influence the choice of Data Management system:
---
- Inward (Employee) vs Outward (Customer) Facing
- How Critical is consistency, or is eventual consistency fine(Every viewer of the data base sees the same thing & also only one person is allowed to make changes at a time)
- Do answers need to be precise, accurate data / complete computation
- Interactive vs Data Analysis
- Does the Data Partition Easily? 

- How complex is the data?
	- flat records
	- files
	- nested structure
- How much heterogeneity in the data?
	- Are all the data types similar
- How much data is there?
- What is the update pattern & how often is it updated & accessed?
	- Append only
	- Read only
	- and many more options
- How sensitive & valuable is the data?
- How much variability in demand 

- How complex is the logic?
- What is the data access pattern?
	- Are there hot spots & cold spots (often accessed or not)
	- Is there locality of access (data close by that is accessed together usually)
- How complex are the access patterns for common operations?
	- Single data item
	- Multiple data items
	- Large chunks of data
- Can the data in use fit in memory?
