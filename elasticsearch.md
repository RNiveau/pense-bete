Get cluster health:
===================

http://localhost:9200/_cluster/health?pretty=true


Assign a shard manually:
========================

```
curl -XPOST 'localhost:9200/_cluster/reroute' -d '{
        "commands" : [ {
              "allocate" : {
                  "index" : "collectd-2017.06.29",
                  "shard" : 1,
                  "node" : "et1-et-01",
                  "allow_primary" : true
              }
            }
        ]
}'
```
