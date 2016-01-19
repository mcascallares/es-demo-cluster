# we should use development version to avoid dot issues
# https://github.com/Ingensi/dockerbeat/issues/64
FROM ingensi/dockerbeat:develop
MAINTAINER Matias Cascallares <matiascas@gmail.com>

RUN apt-get update && apt-get install -y \
	netcat

ADD wait_and_start /wait_and_start
ADD dockerbeat.template.json /etc/dockerbeat/dockerbeat.template.json

CMD ["sh", "/wait_and_start"]