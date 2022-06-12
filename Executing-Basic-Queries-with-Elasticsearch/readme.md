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
-------------------------------------------
```json
GET accounts/_search
{
  "query": {
    "match": {
      "age": "32"
    }
  }
}
```

Response:

```json
{
  "took" : 1,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 52,
      "relation" : "eq"
    },
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "accounts",
        "_id" : "RQgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 1,
          "balance" : 39225,
          "firstname" : "Amber",
          "lastname" : "Duke",
          "age" : 32,
          "gender" : "M",
          "address" : "880 Holmes Lane",
          "employer" : "Pyrami",
          "email" : "amberduke@pyrami.com",
          "city" : "Brogan",
          "state" : "IL"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "WwgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 56,
          "balance" : 14992,
          "firstname" : "Josie",
          "lastname" : "Nelson",
          "age" : 32,
          "gender" : "M",
          "address" : "857 Tabor Court",
          "employer" : "Emtrac",
          "email" : "josienelson@emtrac.com",
          "city" : "Sunnyside",
          "state" : "UT"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "dQgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 121,
          "balance" : 19594,
          "firstname" : "Acevedo",
          "lastname" : "Dorsey",
          "age" : 32,
          "gender" : "M",
          "address" : "479 Nova Court",
          "employer" : "Netropic",
          "email" : "acevedodorsey@netropic.com",
          "city" : "Islandia",
          "state" : "CT"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "fQgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 140,
          "balance" : 26696,
          "firstname" : "Cotton",
          "lastname" : "Christensen",
          "age" : 32,
          "gender" : "M",
          "address" : "878 Schermerhorn Street",
          "employer" : "Prowaste",
          "email" : "cottonchristensen@prowaste.com",
          "city" : "Mayfair",
          "state" : "LA"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "fwgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 145,
          "balance" : 47406,
          "firstname" : "Rowena",
          "lastname" : "Wilkinson",
          "age" : 32,
          "gender" : "M",
          "address" : "891 Elton Street",
          "employer" : "Asimiline",
          "email" : "rowenawilkinson@asimiline.com",
          "city" : "Ripley",
          "state" : "NH"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "wwgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 316,
          "balance" : 8214,
          "firstname" : "Anita",
          "lastname" : "Ewing",
          "age" : 32,
          "gender" : "M",
          "address" : "396 Lombardy Street",
          "employer" : "Panzent",
          "email" : "anitaewing@panzent.com",
          "city" : "Neahkahnie",
          "state" : "WY"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "_wgpWYEB6dOIqGzjArQ5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 467,
          "balance" : 6312,
          "firstname" : "Angelica",
          "lastname" : "May",
          "age" : 32,
          "gender" : "F",
          "address" : "384 Karweg Place",
          "employer" : "Keeg",
          "email" : "angelicamay@keeg.com",
          "city" : "Tetherow",
          "state" : "IA"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "FQgpWYEB6dOIqGzjArU5",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 520,
          "balance" : 27987,
          "firstname" : "Brandy",
          "lastname" : "Calhoun",
          "age" : 32,
          "gender" : "M",
          "address" : "818 Harden Street",
          "employer" : "Maxemia",
          "email" : "brandycalhoun@maxemia.com",
          "city" : "Sidman",
          "state" : "OR"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "ewgpWYEB6dOIqGzjArU6",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 777,
          "balance" : 48294,
          "firstname" : "Adkins",
          "lastname" : "Mejia",
          "age" : 32,
          "gender" : "M",
          "address" : "186 Oxford Walk",
          "employer" : "Datagen",
          "email" : "adkinsmejia@datagen.com",
          "city" : "Faywood",
          "state" : "OK"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "wQgpWYEB6dOIqGzjArU6",
        "_score" : 1.0,
        "_source" : {
          "account_number" : 950,
          "balance" : 30916,
          "firstname" : "Sherrie",
          "lastname" : "Patel",
          "age" : 32,
          "gender" : "F",
          "address" : "658 Langham Street",
          "employer" : "Futurize",
          "email" : "sherriepatel@futurize.com",
          "city" : "Garfield",
          "state" : "OR"
        }
      }
    ]
  }
}
```
----------------------------

```json
GET accounts/_search
{
  "query": {
    "match": {
      "firstname": "huff dale"
    }
  }
}
```

Response:

```json
{
  "took" : 1,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 2,
      "relation" : "eq"
    },
    "max_score" : 6.5032897,
    "hits" : [
      {
        "_index" : "accounts",
        "_id" : "SwgpWYEB6dOIqGzjArQ5",
        "_score" : 6.5032897,
        "_source" : {
          "account_number" : 18,
          "balance" : 4180,
          "firstname" : "Dale",
          "lastname" : "Adams",
          "age" : 33,
          "gender" : "M",
          "address" : "467 Hutchinson Court",
          "employer" : "Boink",
          "email" : "daleadams@boink.com",
          "city" : "Orick",
          "state" : "MD"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "9QgpWYEB6dOIqGzjArQ5",
        "_score" : 6.5032897,
        "_source" : {
          "account_number" : 443,
          "balance" : 7588,
          "firstname" : "Huff",
          "lastname" : "Thomas",
          "age" : 23,
          "gender" : "M",
          "address" : "538 Erskine Loop",
          "employer" : "Accufarm",
          "email" : "huffthomas@accufarm.com",
          "city" : "Corinne",
          "state" : "AL"
        }
      }
    ]
  }
}

```
----------------------------------------------------
```json
GET accounts/_search
{
  "query": {
    "multi_match": {
      "query": "ford",
      "fields": ["firstname", "address"]
    }
  }
}
```

Response:

```json
{
  "took" : 0,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 2,
      "relation" : "eq"
    },
    "max_score" : 6.5032897,
    "hits" : [
      {
        "_index" : "accounts",
        "_id" : "rwgpWYEB6dOIqGzjArs-",
        "_score" : 6.5032897,
        "_source" : {
          "account_number" : 748,
          "balance" : 38060,
          "firstname" : "Ford",
          "lastname" : "Branch",
          "age" : 25,
          "gender" : "M",
          "address" : "926 Cypress Avenue",
          "employer" : "Buzzness",
          "email" : "fordbranch@buzzness.com",
          "city" : "Beason",
          "state" : "DC"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "4QgpWYEB6dOIqGzjArQ5",
        "_score" : 6.501515,
        "_source" : {
          "account_number" : 392,
          "balance" : 31613,
          "firstname" : "Dotson",
          "lastname" : "Dean",
          "age" : 35,
          "gender" : "M",
          "address" : "136 Ford Street",
          "employer" : "Petigems",
          "email" : "dotsondean@petigems.com",
          "city" : "Chical",
          "state" : "SD"
        }
      }
    ]
  }
}

```
--------------

```json
GET accounts/_search
{
  "query": {
    "match_phrase": {
      "address": "Sedgwick street"
    }
  }
}
```

Response:

```json
{
  "took" : 43,
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
    "max_score" : 6.9447823,
    "hits" : [
      {
        "_index" : "accounts",
        "_id" : "XQgpWYEB6dOIqGzjArQ5",
        "_score" : 6.9447823,
        "_source" : {
          "account_number" : 63,
          "balance" : 6077,
          "firstname" : "Hughes",
          "lastname" : "Owens",
          "age" : 30,
          "gender" : "F",
          "address" : "510 Sedgwick Street",
          "employer" : "Valpreal",
          "email" : "hughesowens@valpreal.com",
          "city" : "Guilford",
          "state" : "KS"
        }
      }
    ]
  }
}
```
---------

- Wild Card

```json
GET accounts/_search
{
  "query": {
    "wildcard": {
      "firstname": {
        "value": "h*ll"
      }
    }
  }
}
```
- Compund Queries

```sh
GET accounts/_search
{
  "query": {
    "bool": {
      "must": {
        "term": {"address" : "street"}        
      }
    }
  }
}


GET accounts/_search
{
  "query": {
    "bool": {
      "must": {
        "term" : {"gender": "M"   }     
      }
    }
  }
}

GET accounts/_search
{
  "query": {
    "bool": {
      "must": {
        "term" : {"address": "street"   }     
      },
      "must_not": {
        "term" : { "age" : "27"}
      }
    }
  }
}
```
-------------------------

- Modify scoring in elastic search

```json
GET accounts/_search
{
  "query": {
    "match": {
      "address": "street"
    }
  }
}

GET accounts/_search
{
  "query": {
    "boosting": {
      "positive": {
        "term": {
          "address": "street"
        }
      },
      "negative": {
        "term": {
          "address": "madison"
          
        }
      },
      "negative_boost": 0.2
    }
  }
}
```
---------

- Fuzzy Query

```sh
GET accounts/_search
{
  "query": {
    "match": {
      "city": "edenburg"
    }
  }
}

GET accounts/_search
{
  "query": {
    "fuzzy": {
      "city": "edenburg"
    }
  }
}
```

Response:
```json
{
  "took" : 14,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 2,
      "relation" : "eq"
    },
    "max_score" : 6.5059485,
    "hits" : [
      {
        "_index" : "accounts",
        "_id" : "4wgpWYEB6dOIqGzjArQ5",
        "_score" : 6.5059485,
        "_source" : {
          "account_number" : 397,
          "balance" : 37418,
          "firstname" : "Leonard",
          "lastname" : "Gray",
          "age" : 36,
          "gender" : "F",
          "address" : "840 Morgan Avenue",
          "employer" : "Recritube",
          "email" : "leonardgray@recritube.com",
          "city" : "Edenburg",
          "state" : "AL"
        }
      },
      {
        "_index" : "accounts",
        "_id" : "KwgpWYEB6dOIqGzjArs-",
        "_score" : 5.692705,
        "_source" : {
          "account_number" : 419,
          "balance" : 34847,
          "firstname" : "Helen",
          "lastname" : "Montoya",
          "age" : 29,
          "gender" : "F",
          "address" : "736 Kingsland Avenue",
          "employer" : "Hairport",
          "email" : "helenmontoya@hairport.com",
          "city" : "Edinburg",
          "state" : "NE"
        }
      }
    ]
  }
}

```
-------------

- Range DSL Query

```json
GET accounts/_search
{
  "query": {
    "range": {
      "balance": {
        "gte": 10000
      }
    }
  }
}


GET accounts/_search
{
  "query": {
    "bool": {
      "must": {
        "range" : {
          "age" : {
            "gte" : 30,
            "lte" : 40
          }
        }
      },
      "must_not": {
        "term": {
          "state" : "il"
        }
      }
    }
  }
}
```
