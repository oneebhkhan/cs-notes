**Transaction:** symbolizes a *unit of work* performed within a database. It is often composed of multiple operations. A transaction would be different for databases in different industries. 
	*Example: in the case of a bank when transferring $X from one account to another we will deduct in one account and also deduct total amount from branch, and then add in another account and also update the sum total in the other branch account*

**ACID (Atomicity, Consistency, Isolation, Durability)** is a set of properties of database transactions intended to guarantee validity even in the event of system crashes, power failures, and other errors.

**Atomic:**
Guarantees that all operations in a transaction are treated as a single “unit”, which either succeeds completely or fails completely.

**Consistent:**
Ensures that a transaction can only bring the database from one **valid state** to another by preventing data corruption.
	Consistency in ACID Transactions and [[CAP Theorem]] refer to different concepts. In CAP Theorem, consistency refers to the guarantee of a distributed systems having a shared understanding of the value of a single data element from a read standpoint. It is also referred to as strong consistency or linearizability. CAP's *consistency* is best compared with ACID's *isolation.*
	ACID’s consistency refers to data integrity guarantees that ensure the transition of _the entire database_ from one valid state to another. Such a transition involves strict enforcement of integrity constraints such as data type adherence, null checks, relationships, and more. Given that a single ACID transaction can touch multiple data elements where as CAP’s consistency refers to a single data element, ACID transactions are a stronger guarantee than CAP’s consistency.

**Isolated:**
Determines how and when changes made by one transaction become visible to the other. _[[Serializable Isolation]]_ and _[[Snapshots|Snapshot Isolation]]_ are the top 2 isolation levels from a strictness standpoint. 

**Durable:**
Ensures that the results of the transaction are permanently stored in the system. The modifications must persist even in case of power loss or system failures.

#### Benefits:
1. Absolute data integrity and safety
2. Simplified concurrency and control
	When a DB guarantees transacations with serializable isolation, devs can treat each transaction as it were executeed sequentially - even if it may actually be executed concurrently.
3. Intuitive Data Access logic
4. Future-proofing Database needs

[ACID Transactions for Performant systems](https://www.yugabyte.com/blog/yes-we-can-distributed-acid-transactions-with-high-performance/)


####  Sources:
[Primer on ACID Transactions](https://www.yugabyte.com/blog/a-primer-on-acid-transactions/)
