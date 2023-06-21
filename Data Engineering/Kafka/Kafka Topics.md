
## Topic Partitions
[[Sharding]] in Kafka is called Partitioning. [[B-Trees]]

Topics in Kafka are partitioned, i.e. a topic is spread over a number of "buckets" located on different [[Kafka Brokers]]. <mark style="background: #FFB8EBA6;">The distributed placement is key for scalability because it allows client applications to both **read** and **write** the data from/to many brokers simultaneously</mark>.

When a new event is published to a topic, it is appended to **one** of the topic's partitions based on a given event key, e.g. customer ID. Kafka guarrantees that consumers of a given topic partititon will always read the partition's events in exactly the same order as they are written.
![[topics.png | 600]]

## Replication
Database [[Clustering]] is akin to **replication** in Kafka.
In Kafka, replication means that copies of data in a Kafka Topic are saved in multiple Kafka Brokers. We typically default to a replication factor of 3, with 1 leader and 2 followers.
The unit of replication is each Kafka Topic Partition , therefore <mark style="background: #FFB8EBA6;">each partition has 1 leader and 0 or more followers</mark>. Often there are more partitions than brokers, so the leaders are evenly distributed among brokers.
**All writes** go to the leader of the partition. **Reads** can go to the leader or the followers of the partition. Followers consume messages from the leader just as a normal [[Kafka Consumer]].
