FROM docker.elastic.co/beats/metricbeat:6.4.1
COPY ./metricbeat.yml /usr/share/metricbeat/metricbeat.yml
USER root
RUN chown root:metricbeat /usr/share/metricbeat/metricbeat.yml ;\
    chmod go-w /usr/share/metricbeat/metricbeat.yml ;\
    groupadd docker -g 112 ;\
    usermod -a -G docker metricbeat
USER metricbeat
