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

cluster name -> couchbase-training-cluster

admin username -> Administrator

password -> password

Configure Disk, Memory, Services (click)

      Data (enable and set): 768mb

      Query (enable, no memory setting)

      Index (enable and set): 256mb

      Search (enable and set): 256mb

next and finish

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

## Import Document

We're going to use tool that helps to import data.

- https://docs.couchbase.com/server/current/tools/cbimport-json.html

```

touch tempdata.json 

[
  {
    "key": "mykey1",
    "value": "myvalue1"
  },
  {
    "key": "mykey2",
    "value": "myvalue2"
  },
  {
    "key": "mykey3",
    "value": "myvalue3"
  },
  {
    "key": "mykey4",
    "value": "myvalue4"
  }
]

docker cp tempdata.json couchbase-db:/tmp

docker exec -it couchbase-db /bin/bash

cd /tmp

cbimport json --format list -c http://localhost:8091 -u admin -p 123123 -d 'file://tempdata.json' -b 'couch-bucket' --scope-collection-exp "_default._default" -g "#UUID#" 

```


## Resources

http://e-learning-labs.s3-website-us-west-2.amazonaws.com/cb130j-lab-instructions/

https://www.youtube.com/watch?v=MpqxIkFjbew&list=PL9UhsVQ6a6HMH610-ch5JavzC4MlIIH3j&index=1
