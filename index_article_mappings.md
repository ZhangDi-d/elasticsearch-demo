index article’s mappings and settings ： 

```

{
  "article" : {
    "aliases" : { },
    "mappings" : {
      "properties" : {
        "articleID" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "author_first_name" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          },
          "copy_to" : [
            "new_author_full_name"
          ]
        },
        "author_full_name" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "author_last_name" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          },
          "copy_to" : [
            "new_author_full_name"
          ]
        },
        "content" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "follower_num" : {
          "type" : "long"
        },
        "hidden" : {
          "type" : "boolean"
        },
        "new_author_first_name" : {
          "type" : "text",
          "copy_to" : [
            "new_author_full_name"
          ]
        },
        "new_author_full_name" : {
          "type" : "text"
        },
        "new_author_last_name" : {
          "type" : "text",
          "copy_to" : [
            "new_author_full_name"
          ]
        },
        "postDate" : {
          "type" : "date"
        },
        "sub_title" : {
          "type" : "text",
          "fields" : {
            "std" : {
              "type" : "text",
              "analyzer" : "standard"
            }
          },
          "analyzer" : "english"
        },
        "tag" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "tag_cnt" : {
          "type" : "long"
        },
        "title" : {
          "type" : "text",
          "fields" : {
            "keyword" : {
              "type" : "keyword",
              "ignore_above" : 256
            }
          }
        },
        "userID" : {
          "type" : "long"
        },
        "view_cnt" : {
          "type" : "long"
        }
      }
    },
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
        "provided_name" : "article",
        "creation_date" : "1609156191282",
        "number_of_replicas" : "1",
        "uuid" : "_LaU_8fuTlCsJ9ZvEqUCjA",
        "version" : {
          "created" : "7100199"
        }
      }
    }
  }
}
```
