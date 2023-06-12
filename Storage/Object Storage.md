Object Storage is a computer data storage architecture which works best for static storage, especially for unstructured data, where you **write data once but may need to read it many times**, and typically offers _weaker_ consistency guarrantees (e.g. eventual consistency)
  
While object storage eliminates the need for directories, folders, and other complex hierarchical organization, it’s not a good solution for dynamic data that is changing constantly as you’ll need to rewrite the _entire_ object to modify it. 

In some cases, [[File Storage]] and [[Block Storage]] may still suit your needs depending on your speed and performance requirements.

### Benefits
1. Massive scalability
	- Can easily scale out the **flat architecture** of Object Storage without suffering from limitations of File or Block Storage
2. Reduced Complexity 
3. Searchability
4. Resiliency
5. Cost Efficiency

### Use Cases
1. Cloud Native Applications
2. Big Data Analytics
3. Internet of Things
4. Rich media storage and delivery
5. Backup and Archiving
