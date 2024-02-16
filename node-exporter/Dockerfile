FROM ubuntu

LABEL maintainer="Tania Arutiunian, Sergey Arzumanyan"

WORKDIR /node-exporter

ARG FORMAT=arm64
ARG NODE_EXPORTER_PORT=9100

ADD https://github.com/prometheus/node_exporter/releases/download/v1.5.0/node_exporter-1.5.0.linux-${FORMAT}.tar.gz .

RUN tar xvfz node_exporter-1.5.0.linux-${FORMAT}.tar.gz node_exporter-1.5.0.linux-${FORMAT} && \
    mv node_exporter-1.5.0.linux-${FORMAT}/node_exporter /usr/local/bin && \
    rm -r node_exporter-1.5.0.linux-${FORMAT}*

EXPOSE ${NODE_EXPORTER_PORT}

ENTRYPOINT ["/usr/local/bin/node_exporter"]