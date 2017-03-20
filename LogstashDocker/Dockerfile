FROM logstash:5.2.2
MAINTAINER Rohit Sehgal (rsehgal@iitk.ac.in)
RUN logstash-plugin install logstash-filter-translate
CMD ["-f","/etc/logstash/conf.d"]

