FROM ptipd/uin-base-alpine:1.1_3.11

ARG CFG_ID
ARG APP_BUILD

RUN printf "Build of ${APP_BUILD}, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` >> /etc/BUILD && \
    #
    # install base cli tools:
    apk update && apk upgrade && \
    apk add --no-cache logrotate && \
    #
    # prepare config user:
    addgroup -g ${CFG_ID} cfg && \
    adduser -D -H -u ${CFG_ID} -G cfg -s /sbin/nologin -h /opt cfg && \
    #
    # prepare entrypoint:
    echo '#!/bin/sh' > /app && \
    echo 'crond -f' >> /app && \
    chmod +rx /app && \
    true

ENTRYPOINT /app
