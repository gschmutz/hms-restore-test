# Bluesky to Elasticsearch

In this small tutorial we will be tapping into the Bluesky social media firehose and send the posts via Kafka into Elasticsearch to visualize it over Kibana.

## Configure Platys stack

```bash
platys init -n platys-platform --stack trivadis/platys-modern-data-platform --stack-version develop -f  --structure flat
```

```yaml
KAFKA_enable: true
AKHQ_enable: true
KAFKA_CONNECT_enable: true
KAFKA_CONNECT_UI: true
ELASTICSEARCH_enable: true
KIBANA_enable: true
```

Configure the Elasticsearch connector and the additional SMTs

```yaml
KAFKA_CONNECT_connectors: 'confluentinc/kafka-connect-elasticsearch:15.0.0,confluentinc/connect-transforms:latest'
```

```bash
platys gen
```

## Creating the Bluesky retriever

Create the Kafka topic

```bash
docker exec -ti kafka-1 kafka-topics --bootstrap-server kafka-1:19092 --create --topic bluesky.raw --replication-factor 3 --partitions 8
```

Run the bluesky retriever

```bash
<<<<<<< Updated upstream
docker run --name bluesky-retriever --rm -d -e DESTINATION=kafka -e KAFKA_BROKERS=192.168.1.112:9092 -e KAFKA_TOPIC=bluesky.raw ghcr.io/gschmutz/bluebird:latest
=======
docker run --name bluesky-retriever --rm -d -e DESTINATION=kafka -e KAFKA_BROKERS=10.156.72.251:9092 -e KAFKA_TOPIC=bluesky.raw ghcr.io/gschmutz/bluebird:latest
>>>>>>> Stashed changes
```

Let's see the messages comming in with `kcat` 

```bash
<<<<<<< Updated upstream
kca	t -q -b 192.168.1.112:9092 -t bluesky.raw
=======
kca	t -q -b 10.156.72.251:9092 -t bluesky.raw
>>>>>>> Stashed changes
```

What are the different message types?

```bash
<<<<<<< Updated upstream
kcat -q -b 192.168.1.112:9092 -t bluesky.raw | jq .record.commit.collection
=======
kcat -q -b 10.156.72.251:9092 -t bluesky.raw | jq .record.commit.collection
>>>>>>> Stashed changes
```

Let's view only the `text` of an `app.bsky.feed.post` message

```bash
<<<<<<< Updated upstream
kcat -q -b 192.168.1.112:9092 -t bluesky.raw | jq 'select(.record.commit.collection == "app.bsky.feed.post") | .record.commit.record.text'
=======
kcat -q -b 10.156.72.251:9092 -t bluesky.raw | jq 'select(.record.commit.collection == "app.bsky.feed.post") | .record.commit.record.text'
>>>>>>> Stashed changes
```

## Kafka Connect - Elasticsearch Sink Connector

Add the Elasticsearch connector

```bash
curl -X PUT \
<<<<<<< Updated upstream
  http://192.168.1.112:8083/connectors/elasticsearch-bluesky-sink/config \
=======
  http://10.156.72.251:8083/connectors/elasticsearch-bluesky-sink/config \
>>>>>>> Stashed changes
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -d '{
  "connector.class": "io.confluent.connect.elasticsearch.ElasticsearchSinkConnector",
  "type.name": "_doc",
  "tasks.max": "1",
  "topics": "bluesky.raw",
  "connection.url": "http://elasticsearch-1:9200",
  "key.ignore": "true",
  "key.converter": "org.apache.kafka.connect.storage.StringConverter",
  "schema.ignore": "true",
  "type.name": "kafkaconnect",
  "value.converter": "org.apache.kafka.connect.json.JsonConverter",
  "value.converter.schemas.enable": "false",
  "value.converter.schema.registry.url": "http://schema-registry-1:8081",
  "errors.tolerance": "all",
  "errors.log.include.messages": "true",
  "errors.deadletterqueue.topic.name": "es-sink.bluesky.dlq",
  "errors.log.enable": "false",
  "behavior.on.malformed.documents": "ignore",
  "drop.invalid.message": "true",
  "behavior.on.null.values": "IGNORE",
  "transforms": "filterValue",
  "transforms.filterValue.filter.condition": "$[?(@.record.commit.collection =~ /.*app.bsky.feed.post/)]",
  "transforms.filterValue.filter.type": "include",
  "transforms.filterValue.type": "io.confluent.connect.transforms.Filter$Value"  
}'
```

<<<<<<< Updated upstream
Visulalize the connector in the [Kafka Connect UI](http://192.168.1.112:28103/).
=======
Visulalize the connector in the [Kafka Connect UI](http://10.156.72.251:28103/).
>>>>>>> Stashed changes


## Kibana - Visualize the Posts

<<<<<<< Updated upstream
Navigate to <http://192.168.1.112:5601>
=======
Navigate to <http://10.156.72.251:5601>
>>>>>>> Stashed changes
