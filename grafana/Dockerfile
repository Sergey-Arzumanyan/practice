FROM ubuntu

LABEL maintainer="Tania Arutiunian, Sergey Arzumanyan"

WORKDIR /grafana

ARG GRAFANA_PORT=3000

RUN apt-get update && \
    apt-get install -y apt-transport-https software-properties-common wget && \
    wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key && \
    echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | tee -a /etc/apt/sources.list.d/grafana.list && \
    apt-get update && \
    apt-get install -y grafana

EXPOSE ${GRAFANA_PORT}

ENTRYPOINT ["grafana-server"]

CMD ["--config=/etc/grafana/grafana.ini", "--homepath=/usr/share/grafana"]