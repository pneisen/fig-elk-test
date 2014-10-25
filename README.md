# Fig ELK Stack Test

Test of building an ELK (Elasticseach, Logstash, Kibana) stack with Fig and Docker.

## Installation and use
1. Install [Docker](docker.io).
2. Install [Fig](fig.sh).
3. Clone this repo
4. Adjust Logstash / Elasticsearch configurations
5. fig up
6. nc localhost 3333 < /some/log/file.log
7. http://localhost to see the messages show up in Kibana.

This will create 3 docker containers with Elasticsearch, Kibana, and Logstash running in them and connected to each other. Three ports are exposed for access:
* 3333: Logstash TCP input.
* 9200: Elasticsearch HTTP (The KOPF plugin can be accessed at [http:localhost:9200/_plugin/kopf](http:localhost:9200/_plugin/kopf))
* 80: Kibana web interface.
