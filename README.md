# ELK
Easily deployable ELK stack which is auto configured Implemented on docker With minimilistic configuration

Default configurations have be added in individual docker.
There is kibana.yml
There is elasticsearch.yml
Also There is logstash.conf{i/o separate}

Just put your \*.log files in LogstashDocker/logs/ directory and open kibana it
:)

Sometimes we need to increase vm limit
 ` 
  sudo sysctl -w vm.max_map_count=262144
`
