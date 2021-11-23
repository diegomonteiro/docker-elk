ARG ELK_VERSION

# https://www.docker.elastic.co/
FROM docker.elastic.co/logstash/logstash:${ELK_VERSION}

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json
#RUN logstash-plugin install logstash-input-jdbc

RUN logstash-plugin install logstash-filter-json
RUN logstash-plugin install logstash-filter-geoip
RUN logstash-plugin install logstash-filter-aggregate
RUN logstash-plugin install logstash-filter-mutate

RUN logstash-plugin install logstash-output-http
RUN logstash-plugin install logstash-output-csv
RUN logstash-plugin install logstash-output-file

COPY drivers/mssql/mssql-jdbc-7.4.1.jre8.jar /usr/share/logstash/logstash-core/lib/jars/mssql-jdbc.jar
COPY drivers/postgresql/postgresql-42.2.8.jar /usr/share/logstash/logstash-core/lib/jars/postgresql.jar
