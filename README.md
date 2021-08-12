# Features
  1. Global Distributed (Can be deployed accross regions)
  2. Highly Scalable
  3. Low Latency (Gauranteed end to end latency under 10ms and indexed write under 15ms at 99.99 percentile withing same region)  
  4. Multi-Model (data can be store based on Key-Value, Document based, column based and there are multiple model)
  5. SQL, Cassadra, MongoDb etc API
  6. High Availability (Guaranteed availability setup of SLA 99.99%)
  7. Consistency (SBSCE - Strong, Bounded StaleNess, Session(default), Consistent prefix & Eventual)
  8. Pricing (Based on Request Units(RUs), RUs calculated based on query,memory & CPU usage)
  
# Consistency Levels (SBSCE)
  1. <b>Strong</b> : High consistency with no dirty read data will be consistent in every replication across regions.
  2. <b>Bounded Staleness</b> : This level also allow high consistency although it is not 100% and a lag in operations could be there.
  3. <b>Session</b> : It is highly consistent in withing the same session however outside of the session operations may have lag or no lag, although provide high performance.
  4. <b>Consistent Prefix</b> : Reads are highly consistent to a specific past time or could be current time(but not sure) although performance is very high.
  5. <b>Eventual</b> : There is not gaurantee of the consistency or order however provide highest level of performance with lowest latency.
  
  
  
