FROM ingensi/dockerbeat:1.0.0-rc1
MAINTAINER Matias Cascallares <matiascas@gmail.com>

LABEL co.elastic.release-date="2016-02-11"

RUN apt-get update && apt-get install -y \
	netcat

ADD dockerbeat.template.json /etc/dockerbeat/dockerbeat.template.json

COPY ./docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]
