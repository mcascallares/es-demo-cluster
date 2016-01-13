# Elasticsearch Demo Cluster

## Overview

This docker-compose project creates a Elasticsearch cluster with the following topology:

- 5 data nodes
- 3 dedicated master nodes
- 1 dedicated client node
- 1 kibana node pointing to the client node

This nodes are going to run the latest versions of Elasticsearch and Kibana images available in [Docker Hub](https://hub.docker.com/).

It is very convenient for those situation where you need a more realistic ES deployment than just a couple of nodes running on localhost.


## Requirements

- [docker](https://www.docker.com) 1.9 or later since it relies on the latest Docker networking capabilities
- [docker-compose](https://www.docker.com/docker-compose)


## Usage

To start the cluster:

```
docker-compose --x-networking up
```

Kibana will be available in the following URL:

```
http://<your_docker_host>:5601
```

Cluster endpoint via client node:

```
curl -XGET <your_docker_host>:9200
```

For example to check the nodes in the cluster:

```
curl -XGET <your_docker_host>/_nodes?pretty=true
```
