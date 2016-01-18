FROM ingensi/dockerbeat
MAINTAINER Matias Cascallares <matiascas@gmail.com>

RUN apt-get update && apt-get install -y netcat

ADD wait_and_start /wait_and_start
ADD dockerbeat.template.json /etc/dockerbeat/dockerbeat.template.json

CMD ["sh", "/wait_and_start"]