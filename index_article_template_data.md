template data:


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
      "value" : 6,
      "relation" : "eq"
    },
    "max_score" : 1.0,
    "hits" : [
      {
        "_index" : "article",
        "_type" : "_doc",
        "_id" : "6",
        "_score" : 1.0,
        "_source" : {
          "title" : "this is java and hadoop blog"
        }
      },
      {
        "_index" : "article",
        "_type" : "_doc",
        "_id" : "1",
        "_score" : 1.0,
        "_source" : {
          "view_cnt" : 30,
          "sub_title" : "learning more courses",
          "author_last_name" : "Smith",
          "hidden" : false,
          "new_author_first_name" : "Peter",
          "articleID" : "XHDK-A-1293-#fJ3",
          "title" : "this is java and elasticsearch blog",
          "userID" : 1,
          "content" : "i like to write best elasticsearch article",
          "author_first_name" : "Peter",
          "tag_cnt" : 2,
          "postDate" : "2017-01-01",
          "tag" : [
            "java",
            "hadoop"
          ],
          "new_author_last_name" : "Smith",
          "follower_num" : 5
        }
      },
      {
        "_index" : "article",
        "_type" : "_doc",
        "_id" : "2",
        "_score" : 1.0,
        "_source" : {
          "view_cnt" : 50,
          "sub_title" : "learned a lot of course",
          "author_last_name" : "Williams",
          "hidden" : false,
          "new_author_first_name" : "Smith",
          "articleID" : "KDKE-B-9947-#kL5",
          "title" : "this is java blog",
          "userID" : 1,
          "content" : "i think java is the best programming language",
          "author_first_name" : "Smith",
          "tag_cnt" : 1,
          "postDate" : "2017-01-02",
          "tag" : [
            "java"
          ],
          "new_author_last_name" : "Williams",
          "follower_num" : 10
        }
      },
      {
        "_index" : "article",
        "_type" : "_doc",
        "_id" : "3",
        "_score" : 1.0,
        "_source" : {
          "view_cnt" : 100,
          "sub_title" : "we have a lot of fun",
          "author_last_name" : "Ma",
          "hidden" : false,
          "new_author_first_name" : "Jack",
          "articleID" : "JODL-X-1937-#pV7",
          "title" : "this is elasticsearch blog",
          "userID" : 2,
          "content" : "i am only an elasticsearch beginner",
          "author_first_name" : "Jack",
          "tag_cnt" : 1,
          "postDate" : "2017-01-01",
          "tag" : [
            "hadoop"
          ],
          "new_author_last_name" : "Ma",
          "follower_num" : 25
        }
      },
      {
        "_index" : "article",
        "_type" : "_doc",
        "_id" : "4",
        "_score" : 1.0,
        "_source" : {
          "view_cnt" : 80,
          "sub_title" : "both of them are good",
          "author_last_name" : "Li",
          "hidden" : true,
          "new_author_first_name" : "Robbin",
          "articleID" : "QQPX-R-3956-#aD8",
          "title" : "this is java, elasticsearch, hadoop blog",
          "userID" : 2,
          "content" : "elasticsearch and hadoop are all very good solution, i am a beginner",
          "author_first_name" : "Robbin",
          "tag_cnt" : 2,
          "postDate" : "2017-01-02",
          "tag" : [
            "java",
            "elasticsearch"
          ],
          "new_author_last_name" : "Li",
          "follower_num" : 3
        }
      },
      {
        "_index" : "article",
        "_type" : "_doc",
        "_id" : "5",
        "_score" : 1.0,
        "_source" : {
          "view_cnt" : 10,
          "sub_title" : "haha, hello world",
          "author_last_name" : "Peter Smith",
          "hidden" : false,
          "new_author_first_name" : "Tonny",
          "articleID" : "DHJK-B-1395-#Ky5",
          "title" : "this is spark blog",
          "userID" : 3,
          "content" : "spark is best big data solution based on scala ,an programming language similar to java",
          "author_first_name" : "Tonny",
          "tag_cnt" : 1,
          "postDate" : "2017-03-01",
          "tag" : [
            "elasticsearch"
          ],
          "new_author_last_name" : "Peter Smith",
          "follower_num" : 60
        }
      }
    ]
  }
}
```
