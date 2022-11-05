# Partitioning


### [Kleppmann's Book](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781491903063/)

 - How to not do partitioning: Hash on mod of N nodes

If one tries to hash partitions on N nodes, it can mislead partitions when adding/removing new nodes. Example: if the hash key is 123 on a cluster of 10 nodes, the information is stores on the third (3rd) node (123 % 10), however with the addition of one more node, the same hash key will point to the second node (123 % 11).

- Fixed number of nodes

A solution to the above issue is to have a fixed number of nodes, but enough number of partitions evenly distributed. For example, 1000 partitions, distributed equally among 10 nodes (100 partitions each node). With a hash partitioning (circle hashing), whenever a new node is added, less partitions will need to migrate. 

 - If one is requesting to write/read "foo", how to find the right partition to do it?

*Service discovering* systems like *ZooKeeper* can help. The issue is that it can become a *single point of failure*.
Another solution is to rely on a *gossip protocol* to check where the available service is located, as well as health monitoring and addition/removal of nodes. However, it has the issue of eventual consistency instead the strong provided by a centralised solution like *ZooKeeper*

**obs:** *ZooKeeper* context is cluster coordination.[\[see this StackOverflow discussion\]](%5Bsee%20this%20StackOverflow%5D)