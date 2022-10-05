# couchbase-101



## Install Options

- https://docs.couchbase.com/server/current/install/get-started.html

I would like to choose docker :)

- https://docs.couchbase.com/server/current/install/getting-started-docker.html

`
docker run -d --name couchbase-db -p 8091-8096:8091-8096 -p 11210-11211:11210-11211 couchbase

docker logs couchbase-db

open http://localhost:8091

setup new cluster

cluster name -> couchbase-training

admin username -> admin

password -> 123123

next and finish

`
