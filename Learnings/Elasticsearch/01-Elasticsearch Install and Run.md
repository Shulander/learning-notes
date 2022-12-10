# Run/Install
## Using Docker compose
### `docker-compose.yml`
https://github.com/shazforiot/Elasticsearch-kibana-docker-compose-single-node
```yml
---
version: "3.0"
services:
  elasticsearch:
    container_name: elastic-container
    image: docker.elastic.co/elasticsearch/elasticsearch:7.13.4
    environment:
      - xpack.security.enabled=false
      - "discovery.type=single-node"
    networks:
      - ek-net
    ports:
      - 9200:9200
  kibana:
    container_name: kibana-container
    image: docker.elastic.co/kibana/kibana:7.13.4
    environment:
      - ELASTICSEARCH_HOSTS=http://elastic-container:9200
    networks:
      - ek-net
    depends_on:
      - elasticsearch
    ports:
      - 5601:5601
networks:
  ek-net:
    driver: bridge

```
### Start docker compose

```bash
docker compose up -d
```

### Stop docker compose
```bash
docker compose down
```

## Using Docker
### Start 1st run
https://hub.docker.com/_/elasticsearch
```bash
docker network create somenetwork

docker run -d --name elasticsearch --net somenetwork -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:8.5.2
```
### Stop
```bash
docker stop elasticsearch
```
### Resume
```bash
docker start elasticsearch 
```
### Trace logs
```bash
docker logs elasticsearch -f
```
### Change Password
```bash
docker exec -it elasticsearch /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic -i
```
### Kibana home page
http://localhost:5601
