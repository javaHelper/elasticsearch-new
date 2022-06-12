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
