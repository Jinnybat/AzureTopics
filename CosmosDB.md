# 1. Cosmos DB
# 1.1 Features
  1. Global Distributed (Can be deployed accross regions)
  2. Highly Scalable
  3. Low Latency (Gauranteed end to end latency under 10ms and indexed write under 15ms at 99.99 percentile withing same region)  
  4. Multi-Model (data can be store based on Key-Value, Document based, column based and there are multiple model)
  5. SQL, Cassadra, MongoDb etc API
  6. High Availability (Guaranteed availability setup of SLA 99.99%)
  7. Consistency (SBSCE - Strong, Bounded StaleNess, Session(default), Consistent prefix & Eventual)
  8. Pricing (Based on Request Units(RUs), RUs calculated based on query,memory & CPU usage)
  
# 1.2 Consistency Levels (SBSCE)
  1. <b>Strong</b> : High consistency with no dirty read data will be consistent in every replication across regions.
  2. <b>Bounded Staleness</b> : This level also allow high consistency although it is not 100% and a lag in operations could be there.
  3. <b>Session</b> : It is highly consistent in withing the same session however outside of the session operations may have lag or no lag, although provide high performance.
  4. <b>Consistent Prefix</b> : Reads are highly consistent to a specific past time or could be current time(but not sure) although performance is very high.
  5. <b>Eventual</b> : There is not gaurantee of the consistency or order however provide highest level of performance with lowest latency.

# 1.3 Automatic Indexing
  * It is same as applying indexing to any other database, for the very good read result, however write may have negative impact.
  default indexing applied on every property of each item in a collection/container. Indexing may increate Request Units (RUs) as well.
  Azure also provide manual root path selection for excluding indexing in property too.
 
# 1.4 Indexing Mode
  1. <b>Hash</b> : The index is updated synchronously as you create, update or delete items.
  2. <b>None</b> : Indexing is disabled on the container when you don't need the secondary index.

# 1.5 Indexing Types
  1. <b>Hash</b> : Supports efficient equality queries.
  2. <b>Range</b> : Supports efficient equality queries, range queries, and order by queries.
  3. <b>Spatial</b> : Supports efficient spatial (within and distance) queries. The data type can be Point, Polygon, or LineString.

# 1.6 Partition Keys
  1. <b>Logical Partition</b> : Every container is divided into logical partition based on the partition key, this is done by Azure cosmos DB with distributed data algorithm to increase the performance of the query.
  2. <b>Physical Partition</b> :  Each logic containers are directly mapped to the physical containers where data is actually stored. 

# 1.7 Throughput
  * Throughput means systems capability to process the data generally it is measured in queries handled per second by the DB. In cosmos DB throughput also expressed as Request Units(RUs), Usage of of Request Units are measured based on IO, Memory & CPU.

# 1.8 Recommendation
  1. Cosmos DB performance can be monitored from Metric Page or Azure Monitoring. Reports/Graphs can be fetched based on timeframes, regions, and containers.
  2. Use Replication across the globe at least in two regions if the data is very critical.
  3. Create alerts to check the performance and the RUs requirements continuously.
  4. Create alerts to verify the attacks.
  5. Automated backups are already there. Retention period and frequency can be increased by using the Datafactory.
  6. Cosmos DB access key should be saved inside the vault and not inside the code.
  7. Storage encryption is already managed by Microsoft.
  8. Configure proper permissions to the users using IAM, follow the principle of least privilege.
Default Firewall allows "All Network", this should be configured for whitelisting the specific IPs or limiting the access to particular VNets.
  9. Geo-fencing can be done.
  10. Data in-transit should be accessible through SSL only.

