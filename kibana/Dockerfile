FROM nginx:1.7.6

# Install wget
RUN apt-get update && \
    apt-get install -y ca-certificates wget

# Download and install kibana 3.1.1 in /usr/share/nginx/html 
RUN cd /tmp && \
    wget https://download.elasticsearch.org/kibana/kibana/kibana-3.1.1.tar.gz && \
    tar -xzvf ./kibana-3.1.1.tar.gz && \
    cp -r ./kibana-3.1.1/* /usr/share/nginx/html && \
    rm -rf ./kibana-3.1.1 && \
    rm ./kibana-3.1.1.tar.gz

# Copy over kibana configuration file.
COPY ./conf/config.js /usr/share/nginx/html/config.js
