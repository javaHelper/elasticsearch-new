# Executing Full Text Queries with Elasticsearch

```json
GET accounts/_search
{
  "query": {
    "match": {
      "address": {
        "query": "Holmess",
        "fuzziness": 1
      }
    }
  }
}
```

```json
curl -u elastic:l771Xor0Il65DGUfJyBL https://localhost:9200 -k
{
  "name" : "73dce48a120d",
  "cluster_name" : "docker-cluster",
  "cluster_uuid" : "1bjkFzuzRfqm3qMiXLTe4A",
  "version" : {
    "number" : "8.2.2",
    "build_flavor" : "default",
    "build_type" : "docker",
    "build_hash" : "9876968ef3c745186b94fdabd4483e01499224ef",
    "build_date" : "2022-05-25T15:47:06.259735307Z",
    "build_snapshot" : false,
    "lucene_version" : "9.1.0",
    "minimum_wire_compatibility_version" : "7.17.0",
    "minimum_index_compatibility_version" : "7.0.0"
  },
  "tagline" : "You Know, for Search"
}

```
