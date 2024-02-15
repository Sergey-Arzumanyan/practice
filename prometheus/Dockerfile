FROM ubuntu

LABEL maintainer="Tania Arutiunian, Sergey Arzumanyan"

WORKDIR /prometheus

ARG FORMAT

ADD https://github.com/prometheus/prometheus/releases/download/v2.37.6/prometheus-2.37.6.linux-${FORMAT}.tar.gz .

RUN tar xvfz prometheus-*.tar.gz && \
    rm prometheus-*.tar.gz && \
    mkdir /etc/prometheus /var/lib/prometheus && \
    pwd && ls -la && \
    cd prometheus-2.37.6.linux-${FORMAT} && \
    mv prometheus promtool /usr/local/bin/ && mv consoles/ console_libraries/ /etc/prometheus/

COPY prometheus.yml /etc/prometheus/prometheus.yml

EXPOSE 9090

ENTRYPOINT ["/usr/local/bin/prometheus"]

CMD ["--config.file=/etc/prometheus/prometheus.yml"]
