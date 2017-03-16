FROM alpine

MAINTAINER Rohit Sehgal (rsehgal@iitk.ac.in)

RUN apk update
RUN apk add wget tar

RUN wget https://artifacts.elastic.co/downloads/kibana/kibana-5.2.2-linux-x86_64.tar.gz --no-check-certificate
RUN tar -xzf kibana-5.2.2-linux-x86_64.tar.gz
RUN mv kibana-5.2.2-linux-x86_64 kibana
RUN rm -f kibana-5.2.2-linux-x86_64.tar.gz
RUN apk add nodejs --update 

RUN adduser -D kibana

RUN bundled='NODE="${DIR}/node/bin/node"'\
  && apline_node='NODE="/usr/bin/node"' \
  && sed -i "s|$bundled|$apline_node|g" /kibana/bin/kibana-plugin \
  && sed -i "s|$bundled|$apline_node|g" /kibana/bin/kibana \
  && rm -rf /kibana/node \
  && chown -R kibana:kibana /kibana 

COPY kibana.yml /kibana/config/kibana.yml
WORKDIR /kibana

USER kibana
ENTRYPOINT ["sh"] 
CMD ["/kibana/bin/kibana"]
