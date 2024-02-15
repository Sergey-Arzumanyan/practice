FROM ubuntu

LABEL maintainer="Tania Arutiunian, Sergey Arzumanyan"

WORKDIR /node-exporter

ARG FORMAT

ADD https://github.com/prometheus/node_exporter/releases/download/v1.5.0/node_exporter-1.5.0.linux-${FORMAT}.tar.gz .

RUN tar xvfz node_exporter-*.tar.gz && \
    cd /node-exporter && \
    mv node_exporter-1.5.0.linux-${FORMAT}/node_exporter /usr/local/bin && \
    rm -r node_exporter-1.5.0.linux-${FORMAT}*

EXPOSE 9100

ENTRYPOINT ["/usr/local/bin/node_exporter"]