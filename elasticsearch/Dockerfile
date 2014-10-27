FROM dockerfile/java:oracle-java8

# Download and install elasticsearch 1.3.4 in /opt/elasticsearch
RUN cd /tmp && \
    wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.3.4.tar.gz && \
    tar -xzvf ./elasticsearch-1.3.4.tar.gz && \
    mv ./elasticsearch-1.3.4 /opt/elasticsearch && \
    rm ./elasticsearch-1.3.4.tar.gz

# Copy over elasticsearch startup.
RUN mkdir /app
ADD . /app
RUN chmod +x /app/bin/boot

# Copy over the elastic search config.
COPY ./conf/elasticsearch.yml /opt/elasticsearch/config/elasticsearch.yml

# Elasticsearch HTTP 
EXPOSE 9200

# Install kopf plugin
RUN /opt/elasticsearch/bin/plugin -install lmenezes/elasticsearch-kopf

# Run elasticsearch
ENTRYPOINT ["/app/bin/boot"]
