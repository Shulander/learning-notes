# Getting Started
## Cluster information GET /
```bash
curl -X GET "localhost:9200/"
```
## Cluster information GET /
```bash
curl -X GET "localhost:9200/"
```
## Cluster Health GET /_cluster/health
```bash
curl -X GET "localhost:9200/_cluster/health"
```
## Indices
### List Indices GET /_cat/indices?v&pretty
```bash
curl -X GET "localhost:9200/_cat/indices?v&pretty"
```
### Create Indices PUT /{index_name}
```bash
curl -X PUT "localhost:9200/twitter?pretty"
```
Above will create an index with `shards=1` and `replicas=1` this will cause the health to be yellow
Bellow curl will set the replicas to `0` which will prevent the yellow state
```bash
curl -X PUT "localhost:9200/twitter?pretty" -H 'Content-Type: application/json' -d'
{
  "settings": {
    "index": {
      "number_of_shards": 1,  
      "number_of_replicas": 0 
    }
  }
}
'
```
### Delete Indices DELETE /{index_name}
```bash
curl -X DELETE "localhost:9200/twitter?pretty"
```
## Data
### Add a document PUT /{_index}/{_type}/{_id}
```bash
curl -X PUT "localhost:9200/twitter/tweets/1" -H 'Content-Type: application/json' -d'
{
  "course": "Kafka for Beginners",
  "instructor": "Stephane Maarek",
  "module": "ElasticSearch"
}'
```
### Fetch a document GET /{_index}/{_type}/{_id}
```bash
curl -X GET "localhost:9200/twitter/tweets/1"
```
### Delete a document DELETE /{_index}/{_type}/{_id}
```bash
curl -X DELETE "localhost:9200/twitter/tweets/1"
```
