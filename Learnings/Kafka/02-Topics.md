# Topics
## Cheat Sheet
### List existing topics

```bash
# Docker
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --list

# Kafka Script
./kafka-topics.sh --bootstrap-server localhost:9092 --topic first_topic --list
```

### Create a new topic
```bash
# Docker
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --create \
             --topic first_topic --partitions 3 --replication-factor 1
             
# Kafka Script
./kafka-topics.sh --bootstrap-server localhost:9092 --topic first_topic --create --partitions 3 --replication-factor 1
```

### Describe a topic
```bash
# Docker
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --topic first_topic --describe
             
# Kafka Script
./kafka-topics.sh --bootstrap-server localhost:9092 --topic first_topic --describe
```

### Delete a topic
```bash
docker exec broker \
kafka-topics --bootstrap-server broker:9092 \
             --topic first_topic --delete

# Kafka Script
./kafka-topics.sh --topic first_topic --delete --bootstrap-server localhost:9092
```

