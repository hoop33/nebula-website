---
title: "Nebula Graph Architecture — A Bird’s View"
date: 2019-12-24
description: "Nebula Graph is an open-source, distributed, highly performant graph database. This article explains its technical architecture in detail."
---
# Nebula Graph Architecture — A Bird’s View

Nebula Graph is an open-source project which provides a high performance, a distributed graph database. This article will give a high-level overview of its architecture.

![Nebula Graph Architecture](https://github.com/vesoft-inc/nebula-docs/raw/master/images/Nebula%20Arch.png)


A fully deployed Nebula Graph cluster contains three services, namely Query Service, Storage Service, and Meta Service. Each service has its own executable binary. These binaries can be deployed either on the same set of hosts or on different hosts.

### Meta Service
On the right side of the architecture picture, it shows a cluster of Meta Service. The Meta Service is of a leader/follower architecture. The leader is elected by all Meta Service hosts in the cluster and serves all traffic. Followers stand by and take the updates replicated from the leader. Once the leader dies, one of the followers will be re-elected as the new leader.

The Meta Service not only stores and provides meta information about the graph, such as schema and graph partition information, but also takes the role of the coordinator to orchestra the data movement and to force the leader shift.

Separation of Query and Storage Layers
To the left of the Meta Service is the Nebula Graph's main services. Nebula Graph divides the query execution and the graph storage into two separate services. Above the dotted line is the Query Service, and below the dotted line is the Storage Service.

The separation has several benefits. The most straightforward is that the query layer and storage layer can be expanded or shrunk independently.

The separation also makes the linear horizontal expansion possible.

At last but not least, the separation provides an opportunity to make it possible for the Storage Service to serve multiple computation layers. The current Query Service can be considered as a high-priority computation layer, while an iterative computation framework could be another one.

## Stateless Query Layer
Now let's look at the Query Service. Each individual Query Service host runs a stateless query engine. The Query Service hosts will never communicate with each other. They only read the meta information from the Meta Service and interact with Storage Service. This design makes sure the Query Service cluster can be easily managed by K8s or be deployed on the cloud.

There are two ways to balance the Query Service load. The most common way is to place a load balancer in front of Query Service. The second way is to configure the client library with all Query Service hosts' IP addresses. The client will randomly pick one to connect.

Each query engine takes the request from the client, parses the statement, and generates an Abstract Syntax Tree (AST). Then the AST will be handed over to the execution planner and the optimizer. The final AST will be passed to the executors.

Shared-nothing Distributed Storage Layer
The Storage Service is designed to be a shared-nothing distributed architecture. Each storage host has multiple local key/value stores as the physical data storage. A quorum consensus protocol (we chose RAFT over paxos due to its simplicity) is built on top of the key/value stores. Together, they provide a distributed key/value store. On top of this distributed key/value store, a graph semantic layer is provided to translate the graph operations into key/value operations.

The graph data (vertices and edges) are hashed into multiple partitions. The hash function is straightforward (vertex_id % the_number_of_partitions). A partition is a virtual set of data in Nebula Graph. These partitions are allocated to all storage hosts. The allocation information is stored in the Meta Service and can be accessed by storage hosts and query hosts.
