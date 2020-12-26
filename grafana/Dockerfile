FROM grafana/grafana:latest
# https://hub.docker.com/r/grafana/grafana/tags/

COPY datasources /etc/grafana/provisioning/datasources/
COPY swarmprom_dashboards.yml /etc/grafana/provisioning/dashboards/
COPY dashboards /etc/grafana/dashboards/

RUN grafana-cli plugins install alexanderzobnin-zabbix-app 
RUN grafana-cli plugins install redis-app  
RUN grafana-cli plugins install sbueringer-consul-datasource  
RUN grafana-cli plugins install simpod-json-datasource 
RUN grafana-cli plugins install redis-datasource 
RUN grafana-cli plugins install grafana-simple-json-datasource  
RUN grafana-cli plugins install grafana-worldmap-panel 
RUN grafana-cli plugins install grafana-piechart-panel 
RUN grafana-cli plugins install farski-blendstat-panel 
RUN grafana-cli plugins install jdbranham-diagram-panel 


ENV GF_SECURITY_ADMIN_PASSWORD=admin \
    GF_SECURITY_ADMIN_USER=admin \
    GF_PATHS_PROVISIONING=/etc/grafana/provisioning/
