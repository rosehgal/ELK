FROM alpine

MAINTAINER Rohit Sehgal (rsehgal@iitk.ac.in)

RUN apk --update add openjdk8-jre tar curl

RUN mkdir /elasticsearch
WORKDIR /elasticsearch

RUN curl -L -O https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.2.2.tar.gz 

RUN tar -xf elasticsearch-5.2.2.tar.gz
RUN rm elasticsearch-5.2.2.tar.gz


RUN adduser -D elas
USER elas

RUN chown -R elas /elasticsearch 

COPY elasticsearch.yml /elasticsearch/elasticsearch-5.2.2/config/elasticsearch.yml
COPY logging.yml /elasticsearch/elasticsearch-5.2.2/config/logging.yml

EXPOSE 9200 9300

ENTRYPOINT ["sh"] 
CMD ["/elasticsearch/elasticsearch-5.2.2/bin/elasticsearch"]
