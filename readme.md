## spark-sql-kafka-0-8

Spark Structured Streaming kafka-0-8

## maven
```xml
<dependency>
  <groupId>com.github.harbby</groupId>
  <artifactId>spark-sql-kafka-0-8</artifactId>
  <version>1.0.0-alpha1</version>
</dependency>
```

### use
```
val sparkSession = ...

val kafka08:DataFrame = sparkSession.readStream()
    .format(KafkaDataSource08.class.getName())
    .option("kafka_topic", "test1")
    .option("kafka_broker", "localhost:9092")
    .option("kafka_group_id", "test1")
    .option("auto.offset.reset", "largest")
    .option("zookeeper.connect", "localhost:2181")
    .option("auto.commit.enable", "true")
    .option("auto.commit.interval.ms", "5000")
    .load();
    
kafka08.map(...)    
```