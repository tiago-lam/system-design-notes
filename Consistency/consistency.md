# Consistency

### Fault-tolerant Consensus

Means to come up with a decision that initially multiple nodes compete about it. For example, users trying to get the same seat on a plane, or a theater. Nodes will get to a consensus in order to define who is the winner. 

Nodes should propose a value and the consensus algorithm decides which node proposal will be accepted. In the plane seat example, nodes propose the user ID, and the algorithm defines who is getting the seat. 

### Limitations of consensus
Despite being a breakthrough in the distributed systems, they have the following limitations:

- Needs majority to operate, minimum of two thirds. If the rest is out of use for any reason, only the two third are able to progress, with the others put on a blockage. 
- A fixed number of nodes participate in the voting system. You can't add and remove nodes all the time. Dynamic Membership allows this, but static membership is well understood. 
- Due to the variable delay times of the multiple systems, sometimes nodes can think a leader is not active because of a network issue, specially in geographical distributed contexts. Thus, the time is spent on leader selection way more than on voting, avoiding progress to be made. 