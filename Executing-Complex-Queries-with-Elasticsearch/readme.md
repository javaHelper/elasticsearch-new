# Complex Queries

```json
GET kibana_sample_data_ecommerce/_search
{
  "query": {
    "bool": {
      "filter": [
        { "term": {"currency": "EUR"}},
        { "range": { "order_date": { "gte": "2022-06-15"}}}
      ]
    }
  }
}

```
-----

```json
GET kibana_sample_data_ecommerce/_search
{
  "query": {
    "bool": {
      "filter": [
        { "term": {"currency": "EUR"}},
        { "range": { "order_date": { "gte": "2022-06-15" }}},
        {"term": { "geoip.continent_name": "North America" }}
      ]
    }
  }
}

```
----

GET kibana_sample_data_ecommerce/_settings

```sh
{
  "kibana_sample_data_ecommerce" : {
    "settings" : {
      "index" : {
        "routing" : {
          "allocation" : {
            "include" : {
              "_tier_preference" : "data_content"
            }
          }
        },
        "number_of_shards" : "1",
        "auto_expand_replicas" : "0-1",
        "provided_name" : "kibana_sample_data_ecommerce",
        "creation_date" : "1655107193415",
        "number_of_replicas" : "0",
        "uuid" : "cu4r1YpBQNiHfoPlqlEh3g",
        "version" : {
          "created" : "8020299"
        }
      }
    }
  }
}
```
