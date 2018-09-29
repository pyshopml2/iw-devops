FROM docker.elastic.co/beats/metricbeat:6.4.1
COPY ./metricbeat.yml /usr/share/metricbeat/metricbeat.yml
RUN chown root:metricbeat /usr/share/metricbeat/metricbeat.yml ;\
    chmod go-w /usr/share/metricbeat/metricbeat.yml ;\
    groupadd -g 112 docker ;\
    usermod -a -G docker metricbeat
USER metricbeat
