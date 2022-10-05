# couchbase-101



## Install Options

- https://docs.couchbase.com/server/current/install/get-started.html

## Install Cluster with Docker

- https://docs.couchbase.com/server/current/install/getting-started-docker.html

```

docker run -d --name couchbase-db -p 8091-8096:8091-8096 -p 11210-11211:11210-11211 couchbase:community

docker logs couchbase-db

open http://localhost:8091

setup new cluster

cluster name -> couchbase-training

admin username -> admin

password -> 123123

next and finish with defaults

```

## Create Bucket 

Click Buckets section on left side.

Click Add Bucket button on top-right side.
```
name -> couch-bucket
bucket type -> couchbase 
memory quota -> 512

* This is simple example, we're not going to care of detail on advanced section.

add bucket
```
