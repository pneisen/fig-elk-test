FROM dockerfile/java:oracle-java8

# Download and install logstash 1.4.2 in /opt/logstash
RUN cd /tmp && \
    wget https://download.elasticsearch.org/logstash/logstash/logstash-1.4.2.tar.gz && \
    tar -xzvf ./logstash-1.4.2.tar.gz && \
    mv ./logstash-1.4.2 /opt/logstash && \
    rm ./logstash-1.4.2.tar.gz

# Copy over logstash startup and configuration files.
RUN mkdir /app
ADD . /app
RUN chmod +x /app/bin/boot

# Inbound logstash port
EXPOSE 3333

# Run logstash
ENTRYPOINT ["/app/bin/boot"]
