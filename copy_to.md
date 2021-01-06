1. prepare data:
```
DELETE copy_to_idx
PUT /copy_to_idx
{
  "mappings":{
    "properties": {
      "new_first_name": {
          "type":     "text",
          "copy_to":  "new_full_name" 
      },
      "new_last_name": {
          "type":     "text",
          "copy_to":  "new_full_name" 
      },
      "new_full_name": {
          "type":     "keyword"
      }
  }
  }
}

POST _bulk
{ "create" : { "_index" : "copy_to_idx", "_id" : "1" } }
{ "new_first_name" : "Peter", "new_last_name" : "Smith" }

GET /copy_to_idx/_mapping

GET copy_to_idx/_search
{
  "query": {
    "match": {
      "new_full_name": "Peter Smith"
    }
  }
}
```


2. result:
```
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
      "value" : 0,
      "relation" : "eq"
    },
    "max_score" : null,
    "hits" : [ ]
  }
}

```
