# Producer
```bash
#Docker
docker exec --interactive --tty broker \
kafka-console-producer --bootstrap-server broker:9092 \
            --topic first_topic

#Kafka Script
./kafka-console-producer.sh --bootstrap-server localhost:9092 --topic first_topic

```


# Consumer
```
#Docker
docker exec --interactive --tty broker \
kafka-console-consumer --bootstrap-server broker:9092 \
            --topic first_topic --group my-first-application

#Kafka Script
./kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic first_topic
```
## Flags

1. `--from-beginning`
	- If the consumer does not already have an established offset to consume from, start with the earliest message present in the log rather
