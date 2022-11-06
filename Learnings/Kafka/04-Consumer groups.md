# Consumer groups
## List consumer groups
```bash
#Docker
docker exec broker \
kafka-consumer-groups --bootstrap-server broker:9092 \
                      --list

#Kafka Script
./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --list
```

## Delete consumer group
```bash
#Docker
docker exec broker \
kafka-consumer-groups --bootstrap-server broker:9092 \
                      --group my-first-application \
                      --delete

#Kafka Script
./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group my-second-application --delete
```
## Describe consumer group
```bash
#Docker
docker exec broker \
kafka-consumer-groups --bootstrap-server broker:9092 \
                      --group my-first-application \
                      --describe

#Kafka Script
./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --describe my-first-application
```
## Manipulate Offsets
### to-earliest
```bash
#Docker
docker exec broker \
kafka-consumer-groups --bootstrap-server broker:9092 \
                      --group my-first-application \
                      --reset-offsets --to-earliest \
                      --execute --topic first_topic

#Kafka Script
./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group my-first-application --reset-offsets --to-earliest --execute --topic first_topic
```
### shift-by
```bash
#Docker
docker exec broker \
kafka-consumer-groups --bootstrap-server broker:9092 \
                      --group my-first-application \
                      --reset-offsets \
                      --shift-by -2 \
                      --execute --topic first_topic

#Kafka Script
./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group my-first-application --reset-offsets --shift-by -2 --execute --topic first_topic
```
