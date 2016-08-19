FROM alpine:3.3

ENV NOMAD_VERSION 0.4.1

RUN apk add --no-cache ca-certificates && \
    mkdir -p /tmp/build && \
    cd /tmp/build && \
    wget https://releases.hashicorp.com/nomad/${NOMAD_VERSION}/nomad_${NOMAD_VERSION}_linux_amd64.zip && \
    unzip -d /bin nomad_${NOMAD_VERSION}_linux_amd64.zip && \
    cd /tmp && \
    rm -rf /tmp/build

RUN mkdir -p /nomad/data && \
    mkdir -p /nomad/config

VOLUME /nomad/data

ENTRYPOINT ["nomad"]

CMD ["agent", "-dev"]