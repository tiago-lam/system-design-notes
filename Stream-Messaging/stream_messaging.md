# Stream - Messaging


### [Kleppmann's Book](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/)

### Message Brokers 
A kind of database specifically designed to handle message streams. 
Runs as server, with producers and consumers connected as clients.
Producers write messages to the brokers and consumers get them from the brokers.

### Differences: Message Brokers vs. Databases
Message brokers delete messages as soon as they are successfully delivered. Databases keep the messages, only deleting if they are explicitly commanded to do that.

Queries are time snapshots of the database content. Message brokers don't support arbitrary queries, but they notify consumers about that changes.

#### Load Balancing
Sharing the work of consuming a topic among different consumers
#### Fan Out
Delivering each message to multiple consumers 

#### Acknowledgements
Consumers can break when consuming messages. So brokers need to receive an acknowledge from the consumer before deleting the message from the queue.

#### Log-message based brokers 
Hybrid approach combining the low-latency of message brokers with the durability of databases

### Change Data Capture (CDC)
Messaging systems are suitable for the delivery of CDC since it can capture the data that has changed and replicate the change to other systems. 
**Obs.:** CDC is the process of capturing all the data that has changed in a database, and replicate only the changes in another database

### Complex Event Processing (CEP)
In these systems the relationship between queries and data is reversed to what we see in databases. CEP systems stores queries and when data flows from the streams it looks for a query that matches a pattern.

### Approximation as optimization
Stream analytics systems uses probability algorithms for approximation results. It is a practice used to optimize memory usage.