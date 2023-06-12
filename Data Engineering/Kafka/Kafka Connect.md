Kafka Connect is a framework to stream data into and out of Apache [[Kafka]] - such as from Relational DBs or [[HDFS]]

Conntectors in Kafka Connect define where data should be copied to and from.

A **connector instance** is a logical job that is responsible for managing the copying of data b/w Kafka and another system.

A **connector plugin** are the classes that implement or are used by a connector.

**Source Connectors** push data into Kafka.
**Sink Connectors** push data out of Kafka.