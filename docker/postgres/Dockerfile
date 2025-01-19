FROM postgres:13.13-alpine3.19

ARG TZ=UTC
ENV LANG de_DE.utf8
ENV TZ ${TZ}

RUN ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime && \
    echo ${TZ} > /etc/timezone

RUN apk add --no-cache supervisor postgresql-client

RUN mkdir -p /var/log/postgresql && \
    chown -R postgres:postgres /var/log/postgresql

WORKDIR /var/www/data/database

EXPOSE 5432
