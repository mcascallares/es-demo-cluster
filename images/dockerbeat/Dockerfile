# we should use development version to avoid dot issues
# https://github.com/Ingensi/dockerbeat/issues/64
FROM ingensi/dockerbeat:develop
MAINTAINER Matias Cascallares <matiascas@gmail.com>

LABEL co.elastic.release-date="2016-02-11"

RUN apt-get update && apt-get install -y \
	netcat

ADD dockerbeat.template.json /etc/dockerbeat/dockerbeat.template.json

COPY ./docker-entrypoint.sh /
ENTRYPOINT ["/docker-entrypoint.sh"]