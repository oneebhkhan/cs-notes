## Chapter 1.
1. Reliability
2. Scalability
3. Maintainability
	1. Operability
	2. Simplicity
	3. Evolvability

## Chapter 2 - Data Models

### Relational Model vs. Document Model

_polyglot persistence_?

*impedance mismatch:* disconnect between object oriented and relational data models

For **one-to-many relationship**, these are the approaches:
- Put "many" representations in separate tables with a foreign key reference to one "one" table (traditional SQL Model, prior to SQL:1999)
- Use structured datatypes and XML to store multi-valued data in a single row. Often there is support for querying and indexing inside these documents
- Encode multi-valued data  as JSON or XML documents and store them in the text column in the database. In this scenario, the **application** is responsible for interpreting the structure and content. Typically, the database cannot be used to query for values inside encoded columns


Document Model refers to structured data models like JSON or XML

Document-oriented databases: MongoDB, RethinkDB, CouchDB, Espresso
Features:
- lack of schema
- better locality i.e. all relevant info is in one place, one query is sufficient (e.g. in relational databases you will need to perform multiple queries or complex query with JOIN operations)
- one-to-many relationship implies a tree structure - made explicit by JSON representation

**Note:** As a rule of thumb, if you're duplicating values that could be stored in just one place, the schema is **not** **normalized**.

**Many-to-One** AND **Many-to-Many**

Initially the most popular data model was the **hierarchical model**. Limitations with this model resulted in the creation of:
1. **Network model** 
   However it was not widely adopted because of severe limitations with accessing records from one to another 
   i.e. had to follow an _access path_ which had to be maintained by the application developer. 
   This would get increasingly complicated if multiple records had multiple parents. 
   Code for both querying and updating the database became complicated.
2. **Relational model**
   Most widely adopted data model. Each row represents a record, and each table is essentially a collection of rows (tuples).
   Can insert a new row into any table w/o worrying about foreign key relationships (although those constraints can be imposed).
   Query Optimizer automatically decides how to best execute the query in which order and which indexes to use.

**Document Databases** use the hierarchical model for one-to-many relationships. 
However for many-to-one or many-to-many relationships they opt for the same approach as relational databases. i.e. _document reference_ (aka foreign key in relational model)