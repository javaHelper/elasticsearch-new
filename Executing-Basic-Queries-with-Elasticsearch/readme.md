# Executing Basic Queries with Elasticsearch

- Search for DevTools

<img width="1512" alt="Screenshot 2022-06-12 at 11 58 45 PM" src="https://user-images.githubusercontent.com/54174687/173247903-a4300d54-fea3-4c67-9ddf-5523e81e5fa0.png">


```json
GET accounts/_search
{
  "query": {
    "match": {
      "lastname": "Smith"
    }
  }
}
```

Response:

```json 
{
  "took" : 2,
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
    "max_score" : 6.5032897,
    "hits" : [
      {
        "_index" : "accounts",
        "_id" : "MwgpWYEB6dOIqGzjArg9",
        "_score" : 6.5032897,
        "_source" : {
          "account_number" : 516,
          "balance" : 44940,
          "firstname" : "Roy",
          "lastname" : "Smith",
          "age" : 37,
          "gender" : "M",
          "address" : "770 Cherry Street",
          "employer" : "Parleynet",
          "email" : "roysmith@parleynet.com",
          "city" : "Carrsville",
          "state" : "RI"
        }
      }
    ]
  }
}

```
