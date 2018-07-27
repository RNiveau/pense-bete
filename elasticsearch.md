Get cluster health:
-------------------

curl http://localhost:9200/_cluster/health?pretty=true


Assign a shard manually:
------------------------

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

List all nodes:
---------------

curl http://localhost:9200/_nodes

List indices:
-------------

curl 'localhost:9200/_cat/indices?format=json&pretty=true'

curl 'localhost:9200/_cat/indices'

Snapshot:
---------
```
Create snapshot repository:
curl localhost:9200/_snapshot/backup -X PUT -d '{"type": "fs", "settings": {"location": "/data/backup/elasticsearch/es_backup"}}'

Create the snapshot:
curl -X PUT 'localhost:9200/_snapshot/backup/snapshot_1?wait_for_completion=true'

Close indices:
curl -X POST localhost:9200/fieldheuristic/_close

Restore:
curl -X POST localhost:9200/_snapshot/backup/snapshot_1/_restore
```

Useful links:
-------------

https://www.elastic.co/blog/how-many-shards-should-i-have-in-my-elasticsearch-cluster
https://www.elastic.co/guide/en/elasticsearch/guide/current/routing-value.html

