# https://www.docker.elastic.co/
FROM docker.elastic.co/kibana/kibana:7.10.2
USER kibana
ARG ELASTIC_VERSION=7.10.2
ARG WAZUH_VERSION=4.1.2
ARG WAZUH_APP_VERSION="${WAZUH_VERSION}_${ELASTIC_VERSION}"	

WORKDIR /usr/share/kibana/
# RUN ./bin/kibana-plugin remove wazuh
RUN rm -rf /usr/share/kibana/optimize/bundles
RUN chown -R kibana:kibana /usr/share/kibana/data
RUN chown -R kibana:kibana /usr/share/kibana/plugins

RUN mkdir -p /usr/share/kibana/data/wazuh/config

RUN ./bin/kibana-plugin install https://packages.wazuh.com/4.x/ui/kibana/wazuh_kibana-4.1.2_7.10.2-1.zip

# add copy for yml file 
RUN chown kibana:kibana /usr/share/kibana/data/wazuh/config/
RUN chmod 600 /usr/share/kibana/data/wazuh/config/


