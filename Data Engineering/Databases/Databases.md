#### Table of Contents
[[Databases#Introduction |Introduction]]
[[Relational]]
[[Non-Relational]]

[[Distributed Databases]]

[[ACID Transactions]]
[[BASE Operations]]

[[Sharding]]
[[Clustering]]

[[Database Storage Engines]]

[[SQLite]]

[[NoSQL]]

#### Introduction
Prior to databases there were file-based systems for record keeping. They faced the following issue, making them undesirable:
- data security (anyone who can access the file would be able to modify it - ??)
- concurrency (typically only one user can access a file)
- data inconsistency (inconsistency between copies of data)
- data redundancy (replication of the same data in multiple places)
- difficulty in access.

A database system comprises of a **database** and a **database management system (DBMS)**. 

Typically a database has the following characteristics:
1. Self Describing nature
2. Insulation b/w program and data
3. Support for multiple views
4. Data sharing and supporting multi-user systems

This then allows us to have the following benefits: 
1. Reduced data redundancy (except where required for system performance improvement)
2. Data sharing
3. Enforcement of integrity [[DB Constraints|constraints]]
4. Restriction of Unauthorized Access
5. Backup and recovery facilities
