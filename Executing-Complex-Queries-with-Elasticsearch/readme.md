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
--------

```json
PUT geo-index
{
  "mappings": {
    "properties": {
      "geo": {
        "type": "nested"
      }
    }
  }
}
```

Response:

```json
{
  "acknowledged" : true,
  "shards_acknowledged" : true,
  "index" : "geo-index"
}
```

```json
PUT geo-index/_doc/1
{
  "group" : "customers",
  "geo" : [
    {
      "city" : "Boston",
      "state": "Massachusetts"
    },
    {
      "city" : "Atlanta",
      "state": "Georgia"
    }
  ]
}

PUT geo-index/_doc/2
{
  "group" : "customers",
  "geo" : [
    {
      "city" : "Denver",
      "state": "Colorado"
    },
    {
      "city" : "Jackson",
      "state": "Mississippi"
    }
  ]
}
```

Response:

```json
{
  "_index" : "geo-index",
  "_id" : "1",
  "_version" : 1,
  "result" : "created",
  "_shards" : {
    "total" : 2,
    "successful" : 1,
    "failed" : 0
  },
  "_seq_no" : 0,
  "_primary_term" : 1
}
```

# Nested Queries

```json
GET geo-index/_search
{
  "query": {
    "nested": {
      "path": "geo",
      "query": {
        "bool": {
          "must": [
            {"match": { "geo.city": "Boston" }},
            {"match": { "geo.state": "Massachusetts" }}
          ]
        }
      }
    }
  }
}

```

# Percololated Queries

```json
PUT /alerts-index
{
  "mappings": {
    "properties": {
      "threashold" : {
        "type": "long"
      },
      "price" : {
        "type": "long"
      },
      "query": {
        "type" : "percolator"
      }
    }
  }
}
```


```json
PUT /alerts-index/_doc/1
{
  "threashold" : 125,
  "query": {
    "bool": {
      "must" : {
        "query_string" : {
          "default_field": "query-field",
          "query": "price:>100"
        }
      }
    }
  }
}
```

```json
GET /alerts-index/_search
{
  "query": {
    "match_all": {}
  }
}
```

Response:

```json
{
  "took" : 918,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 1,
      "relation" : "eq"
    },
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "alerts-index",
        "_id" : "1",
        "_score" : 1.0,
        "_source" : {
          "threashold" : 125,
          "query" : {
            "bool" : {
              "must" : {
                "query_string" : {
                  "default_field" : "query-field",
                  "query" : "price:>100"
                }
              }
            }
          }
        }
      }
    ]
  }
}
```

```json
GET /alerts-index/_search
{
  "query": {
    "percolate": {
      "field": "query",
      "document": {
        "price": 150
      }
    }
  }
}
```

Response:

```json
{
  "took" : 31,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 1,
      "relation" : "eq"
    },
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "alerts-index",
        "_id" : "1",
        "_score" : 1.0,
        "_source" : {
          "threashold" : 125,
          "query" : {
            "bool" : {
              "must" : {
                "query_string" : {
                  "default_field" : "query-field",
                  "query" : "price:>100"
                }
              }
            }
          }
        },
        "fields" : {
          "_percolator_document_slot" : [
            0
          ]
        }
      }
    ]
  }
}

```
---------

```json
GET /kibana_sample_data_ecommerce/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "geoip.continent_name": "North America"
          }
        },
        {
          "match": {
            "manufacturer": "Low Time Media"
          }
        }
      ]
    }
  }
}
```

Response:

```json
GET /kibana_sample_data_ecommerce/_search
{
  "query": {
    "bool": {
      "filter": [
        {
          "term": {
            "customer_gender": "MALE"
          }
        },
        {
          "term": {
            "geoip.continent_name": "North America"
          }
        }
      ]
    }
  }
}
```
