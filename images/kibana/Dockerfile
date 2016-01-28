FROM kibana:latest
MAINTAINER Matias Cascallares <matiascas@gmail.com>

LABEL co.elastic.release-date="2016-01-28"

RUN gosu kibana kibana plugin -i elastic/sense
RUN gosu kibana kibana plugin -i kibana/timelion