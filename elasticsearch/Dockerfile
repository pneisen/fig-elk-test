FROM dockerfile/java:oracle-java8

# Download and install elasticsearch 1.3.4 in /opt/elasticsearch
RUN cd /tmp && \
    wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.3.4.tar.gz && \
    tar -xzvf ./elasticsearch-1.3.4.tar.gz && \
    mv ./elasticsearch-1.3.4 /opt/elasticsearch && \
    rm ./elasticsearch-1.3.4.tar.gz

# Copy over elasticsearch startup and configuration files.
RUN mkdir /app
ADD . /app
RUN chmod +x /app/bin/boot

# Elasticsearch HTTP 
EXPOSE 9200

# Install kopf plugin
RUN /opt/elasticsearch/bin/plugin -install lmenezes/elasticsearch-kopf

# Run elasticsearch
ENTRYPOINT ["/app/bin/boot"]
