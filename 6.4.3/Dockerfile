FROM kalicki2k/alpine-base:3.9

MAINTAINER Sebastian Kalicki (https://github.com/kalicki2k)

COPY Dockerfiles /

RUN apk update && apk upgrade && \
    apk add elasticsearch && \
    adduser -D -h /usr/share/java/elasticsearch elasticsearch && \
    unlink /usr/share/java/elasticsearch/plugins && \
    mkdir -p /usr/share/java/elasticsearch/plugins /usr/share/java/elasticsearch/config /usr/share/java/elasticsearch/data && \
    cp /etc/elasticsearch/* /usr/share/java/elasticsearch/config && \
    chown -R elasticsearch:elasticsearch /usr/share/java/elasticsearch && \
    chmod +x /entrypoint.sh && \
    rm -rf /var/cache/apk/*

USER elasticsearch

WORKDIR /usr/share/java/elasticsearch

EXPOSE 9200 9300

ENTRYPOINT ["/entrypoint.sh"]
CMD ["/usr/share/java/elasticsearch/bin/elasticsearch"]