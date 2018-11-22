FROM docker.elastic.co/beats/metricbeat:6.4.1
ARG DB_USER
ARG DB_PASSWORD
ENV DB_USER=${DB_USER}
ENV DB_PASSWORD=${DB_PASSWORD}
COPY ./metricbeat.yml /usr/share/metricbeat/metricbeat.yml
COPY ./system.yml /usr/share/metricbeat/modules.d/system.yml
COPY ./nginx.yml /usr/share/metricbeat/modules.d/nginx.yml
COPY ./mongodb.yml /usr/share/metricbeat/modules.d/mongodb.yml
USER root
RUN chown root:metricbeat /usr/share/metricbeat/metricbeat.yml ;\
    chown root:metricbeat /usr/share/metricbeat/modules.d/system.yml ;\
    chown root:metricbeat /usr/share/metricbeat/modules.d/nginx.yml ;\
    chmod go-w /usr/share/metricbeat/metricbeat.yml ;\
    chmod go-w /usr/share/metricbeat/modules.d/system.yml ;\
    chmod go-w /usr/share/metricbeat/modules.d/nginx.yml ;\
    chmod go-w /usr/share/metricbeat/modules.d/mongodb.yml ;\
    groupadd docker -g 112 ;\
    usermod -a -G docker metricbeat
USER metricbeat
