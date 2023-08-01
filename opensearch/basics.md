## What is it?

- It is a distributed search and analytics engine that helps in analysing large amounts of data to provide visual charts that present meaningful information (opensearch dashboard) and provide search functionlaity on this data making it easy for users to explore their data..
- It is a managed service, aws takes care of deploying the necessary services to handle this functionality.

## Functioning:

- When opensearch service is created/started - it creates a cluster,

  - provisions the necessary infrastructure, such as EC2 instances and EBS volumes.
    - EBS is elastic block storage that provides persistent, resizable storage volumes for use with EC2 instances.
  - installs the OpenSearch software on the EC2 instances.
  - creates a cluster with the specified number of nodes.
  - assigns shards to the nodes in the cluster.
		-	Shards will help in evenly distributing the incoming data among the nodes.
		-	If a doc has to be added to a specific shard, it can be specified by passing `_routing` while making API call.
		-	If not passed, it will take the hash of the id, take its remainder/modulo
  - starts the OpenSearch service on the nodes in the cluster.

- Two clusters are created, primary and standby. Primary stores all the data, and the standby cluster is a copy of primary to ensure availability of the domain if the primary cluster fails.

- When a new cluster is created, it consist of one or more master nodes and multiple data nodes.
- Each node is an EC2 instance which runs the opensearch software.
- A small cluster with a few hundred gigabytes of data may only need two or three nodes. A large cluster with terabytes or petabytes of data may need dozens or even hundreds of nodes.
- For high availability, it is recommended to have atleast 3 data nodes.
- A cluster can be scaled up or down by adding or removing nodes.
- A single cluster can spread across multiple AZs in the same region. This helps to improve the availability of the cluster in case of an AZ failure.

## Advantages:

- Since it is distributed, large amount of data is split into smaller chunks and stored on different nodes - increasing performance and handling failures.
- Scalability: OpenSearch can be scaled horizontally by adding more nodes to the cluster. This allows you to handle large volumes of data without having to upgrade your existing nodes.
- High Availability: AWS OpenSearch Service automatically distributes your data across multiple Availability Zones (AZs) within a region to provide high availability and fault tolerance. If a node or an entire AZ fails, OpenSearch Service automatically handles the failover and replication, ensuring that your data remains accessible.
- Performance: The distributed architecture of OpenSearch can improve performance by caching data on the nodes that are processing it.
- AWS handles

## Cost:

- Distributed system is more expensive as hardware and software for each node is billed.

## Load data into opensearch:

- API:
  - Create a new index in OpenSearch.
  - Create a JSON document that represents the data that you want to index.
  - Use the POST method to index the document in OpenSearch.

```
curl -X POST -u 'username:password' 'http://localhost:9200/my_index/my_type/1' -H 'Content-Type: application/json' -d '{ "name": "John Doe", "age": 30 }'
```

- This code would index a document with the name "John Doe" and the age 30 in the index my_index and the type my_type.

- Opensearch CLI:
- Third party tools: logstash, kibana

```

```


## Creating index:
-	PUT https://search-demodomain2-vo2cbtzdc53o2yvygr6kntcqmu.ap-south-1.es.amazonaws.com/products
<!-- -	Authorization: Basic admin:password -->
-	Setup aws signature
-	Body: {
  "settings": {
    "number_of_shards": 3,
    "number_of_replicas": 2
  }
}

### Adding doc:
-	POST https://search-demodomain2-vo2cbtzdc53o2yvygr6kntcqmu.ap-south-1.es.amazonaws.com/<indexname>/_doc/<docid?>
<!-- -	Authorization: Basic admin:password -->
-	Content-Type: application/json
-	Body: {
  "name": "John Doe",
  "age": 30,
  "email": "john.doe@example.com"
}

doc id auto created if not passed

### Fetching doc:
-	GET https://search-demodomain2-vo2cbtzdc53o2yvygr6kntcqmu.ap-south-1.es.amazonaws.com/products/_doc/<docid>
<!-- -	Authorization: Basic admin:password -->

### Update:
POST https://search-demodomain2-vo2cbtzdc53o2yvygr6kntcqmu.ap-south-1.es.amazonaws.com/products/_doc/<docid>

### Search:
GET https://search-demodomain2-vo2cbtzdc53o2yvygr6kntcqmu.ap-south-1.es.amazonaws.com/products/_search?q=name:mac