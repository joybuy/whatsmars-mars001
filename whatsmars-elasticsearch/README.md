https://www.elastic.co/cn/downloads/past-releases/elasticsearch-6-4-3

### ES代替关系型数据库读写分离
对于关系型数据库，当读请求数远大于写请求数时，读请求会影响写请求的性能，此时我们常用的做法是读写分离。
数据库读写分离操作简单，但遇到跨表甚至跨库查询时，会受到分布式数据库中间件支持能力的限制，而且数据库也
无法承载海量数据的查询。此时应考虑同步写ES，对于实时性要求不高和那些复杂的查询直接走ES，少部分实时性
要求极高的请求仍走关系型数据库，这种情况下完全不用再做关系型数据库读写分离。

### 日志采集与搜索 ELK
Data -> Logstash -> Kafka -> Logstash -> Elasticsearch -> Kibana