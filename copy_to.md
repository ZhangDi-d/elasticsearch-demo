## copy_to field type => keyword

### 1. prepare data:
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


### 2. result:
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


## copy_to field type => search_as_you_type

### 1. prepare data 
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
          "type":     "search_as_you_type"
      }
  }
  }
}

POST _bulk
{ "create" : { "_index" : "copy_to_idx", "_id" : "1" } }
{ "new_first_name" : "Peter", "new_last_name" : "Smith" }
{ "create" : { "_index" : "copy_to_idx", "_id" : "2" } }
{ "new_first_name" : "Park", "new_last_name" : "Smith" }

GET /copy_to_idx/_mapping



```

### 2. when input 'p':
```
GET copy_to_idx/_search
{
  "query": {
    "multi_match": {
      "query": "p",
      "type": "bool_prefix", 
      "fields": ["new_full_name"]
    }
  }
}
```

result :
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
      "value" : 2,
      "relation" : "eq"
    },
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "copy_to_idx",
        "_type" : "_doc",
        "_id" : "1",
        "_score" : 1.0,
        "_source" : {
          "new_first_name" : "Peter",
          "new_last_name" : "Smith"
        }
      },
      {
        "_index" : "copy_to_idx",
        "_type" : "_doc",
        "_id" : "2",
        "_score" : 1.0,
        "_source" : {
          "new_first_name" : "Park",
          "new_last_name" : "Smith"
        }
      }
    ]
  }
}

```

### 3. when input 'pe' :
```
GET copy_to_idx/_search
{
  "query": {
    "multi_match": {
      "query": "pe",
      "type": "bool_prefix", 
      "fields": ["new_full_name"]
    }
  }
}
```
result:
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
      "value" : 1,
      "relation" : "eq"
    },
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "copy_to_idx",
        "_type" : "_doc",
        "_id" : "1",
        "_score" : 1.0,
        "_source" : {
          "new_first_name" : "Peter",
          "new_last_name" : "Smith"
        }
      }
    ]
  }
}

```

