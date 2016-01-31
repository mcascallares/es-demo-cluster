# Elasticsearch Demo Cluster

## Overview

This docker-compose project creates a Elasticsearch cluster with the following topology:

- 5 data nodes
- 3 dedicated master nodes
- 1 dedicated client node
- 1 kibana node pointing to the client node
	- [Timelion plugin](https://github.com/elastic/timelion) installed
	- [Sense plugin](https://github.com/elastic/sense) installed
- 1 [dockerbeat](https://github.com/Ingensi/dockerbeat) node submitting container metrics to Elasticsearch

It is very convenient for those situation where you need a more realistic ES deployment than just a couple of nodes running on localhost.


## Requirements

- [docker](https://www.docker.com) 1.9 or later since it relies on the latest Docker networking capabilities
- [docker-compose](https://www.docker.com/docker-compose)


## Usage

To start the cluster:

```
> docker-compose --x-networking up
```

Kibana will be available in the following URL:

```
http://<your_docker_host>:5601
```

Cluster endpoint via client node:

```
> curl -XGET <your_docker_host>:9200
```

For example to check the nodes in the cluster:

```
> curl -XGET <your_docker_host>/_nodes?pretty=true
```


## Kibana Dashboards

To visualize the Dockerbeat dashboard follow the following steps:

1. Configure an index pattern with the pattern 'dockerbeat-*'
2. Import visualizations and dashboard in kibana-dashboards/dockerbeat.json
3. Enjoy

![Dockerbeat Dashboard](https://raw.githubusercontent.com/mcascallares/es-demo-cluster/master/screenshots/dockerbeat-dashboard.png)
