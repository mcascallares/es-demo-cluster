FROM kibana:4.4.0
MAINTAINER Matias Cascallares <matiascas@gmail.com>

LABEL co.elastic.release-date="2016-02-03"

ADD https://download.elasticsearch.org/kibana/timelion/timelion-latest.tar.gz /timelion.tar.gz
ADD https://download.elasticsearch.org/elastic/sense/sense-latest.tar.gz /sense.tar.gz

RUN chown kibana /timelion.tar.gz
RUN chown kibana /sense.tar.gz

RUN gosu kibana kibana plugin --install timelion --url file:///timelion.tar.gz
RUN gosu kibana kibana plugin --install sense --url file:///sense.tar.gz