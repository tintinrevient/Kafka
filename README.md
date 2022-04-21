# Kafka

## Installation

1. Download the binary from https://kafka.apache.org/downloads

2. Run a dummy test:

```bash
$ ./bin/kafka-storage.sh random-uuid
IFFFDzvqQPeL7t6Z5h09fg

$ ./bin/kafka-storage.sh format -t IFFFDzvqQPeL7t6Z5h09fg -c ./config/kraft/server.properties
Formatting /tmp/kraft-combined-logs

$ ./bin/kafka-server-start.sh ./config/kraft/server.properties

$ ./bin/kafka-topics.sh --create --topic foo --partitions 1 --replication-factor 1 --bootstrap-server localhost:9092
Created topic foo.

$ ./bin/kafka-console-producer.sh --topic foo --bootstrap-server localhost:9092
>test message

$ ./bin/kafka-console-consumer.sh --topic foo --bootstrap-server localhost:9092 --from-beginning
test message
````

## References

* https://www.confluent.io/blog/kafka-without-zookeeper-a-sneak-peek/
* https://github.com/apache/kafka/blob/6d1d68617ecd023b787f54aafc24a4232663428d/config/kraft/README.md
* https://github.com/confluentinc/schema-registry
