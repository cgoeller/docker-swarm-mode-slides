FROM docker.elastic.co/elasticsearch/elasticsearch-oss:6.1.1

USER root

RUN yum install -y bind-utils
COPY es-docker /usr/share/elasticsearch/bin/
RUN chmod +x /usr/share/elasticsearch/bin/es-docker

USER elasticsearch
# Comment out Xms and Xms in jvm.options file
RUN sed -e '/^-Xms/s/^/#/g' -i config/jvm.options
RUN sed -e '/^-Xmx/s/^/#/g' -i config/jvm.options
RUN eval ${ES_JAVA_OPTS:-} && \
    elasticsearch-plugin install --silent --batch https://distfiles.compuscene.net/elasticsearch/elasticsearch-prometheus-exporter-6.1.1.0.zip

ENV ES_JAVA_OPTS="-Xms512m -Xmx512m -XX:MetaspaceSize=64m -XX:MaxMetaspaceSize=256m"

ENTRYPOINT [ "/usr/share/elasticsearch/bin/es-docker" ]
