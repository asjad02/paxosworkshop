This repo has example code for the distributed system workshop.
For building, just run './gradlew clean assemble'
#Assignments
1. Make KVStore durable with write ahead log.
2. Pass the WalBackedKVStoreTest
   Append the key values added to the kv store into write ahead log
2. Make quorum test pass. Complete WriteQuorumCallback
3. Make readRepair pass. Complete ReadQuorumCallback
3. Pass QuorumReadWriteTest#nodesShouldRejectRequestsFromPreviousGenerationNode
   Add logic to reject requests from older generation in QuorumKVStore#handleSetValueRequest


---
## Notes
1. Basic Quorum
- availability : successful write : which leads to partial write
- have to wait for read repairs to ensure consistency: *Eventual Consistency*
- write failed only 1 server was successful
- 2 diff clients connect diff server: diff values for same query :meh:
- 

1. Fault Tolerance quorum


# Problems in Distributed System
- Split Brain
Split brain in a distributed system is a problem that can occur in consistent systems. 
If a network partition occurs in a consistent system then one side or the other (or both)
of the partition needs to stop responding to requests to maintain the consistency guarantee. 
> If both sides continue to respond to reads and writes while they are unable to communicate with each other they will diverge and no longer be consistent.
This state where both sides of the partition remain available is called split brain.
https://en.m.wikipedia.org/wiki/Split-brain_(computing)
 
[reference](https://qr.ae/pGVjZc)

- 