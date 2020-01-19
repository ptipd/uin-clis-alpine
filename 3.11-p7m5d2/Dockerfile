FROM ptipd/uin-clis-alpine:1.1_3.11-cron

ARG CFG_ID
ARG APP_BUILD

RUN printf "Build of ${APP_BUILD}, date: %s\n" `date -u +"%Y-%m-%dT%H:%M:%SZ"` >> /etc/BUILD && \
    #
    # install base cli tools:
    apk update && apk upgrade && \
    apk add --no-cache git \
        php7-intl php7-pdo_mysql php7-mbstring php7-opcache \
        php7-ldap php7-gd php7-json php7-curl php7-pdo php7-mysqli php7-simplexml \
	mysql-client openldap-clients && \
    true
