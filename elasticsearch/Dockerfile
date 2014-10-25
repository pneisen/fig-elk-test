FROM dockerfile/java:oracle-java8

# Download and install elasticsearch 1.1.1 in /opt/elasticsearch
RUN cd /tmp && \
    wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.1.1.tar.gz && \
    tar -xzvf ./elasticsearch-1.1.1.tar.gz && \
    mv ./elasticsearch-1.1.1 /opt/elasticsearch && \
    rm ./elasticsearch-1.1.1.tar.gz

# Copy over logstash startup and cnfiguration files.
RUN mkdir /app
ADD . /app
RUN chmod +x /app/bin/boot

# Inbound logstash port
EXPOSE 9200

# Run logstash
ENTRYPOINT ["/app/bin/boot"]
