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

