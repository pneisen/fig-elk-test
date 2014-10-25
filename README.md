# Fig ELK Stack Test

Test of building an ELK (Elasticseach, Logstash, Kibana) stack with Fig and Docker.

## Installation
1. Install [Docker](docker.io).
2. Install [Fig](fig.sh).
3. Clone this repo
4. fig up

This will create 3 docker containers with Elasticsearch, Kibana, and Logstash running in them and connected to each other. Three ports are exposed for access:
* 3333: Logstash TCP input.
* 9200: Elasticsearch HTTP (The KOPF plugin can be accessed at [http:localhost:9200/_plugin/kopf](http:localhost:9200/_plugin/kopf))
* 80: Kibana web interface.
