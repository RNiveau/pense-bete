Connect to database:
--------------------
/OPT/cassandra/dsc-cassandra/bin/cqlsh -k database host


Status database:
----------------
/OPT/cassandra/dsc-cassandra/bin/nodetool status posc


Delete a cluster node:
----------------------
/OPT/cassandra/dsc-cassandra/bin/nodetool removenode %ID%


Describe cluster:
-----------------
/OPT/cassandra/dsc-cassandra/bin/nodetool describecluster


