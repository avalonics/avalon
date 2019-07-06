FROM php:7.3.6-fpm-alpine3.10

RUN apk update

RUN set -ex \
  && apk --no-cache add \
    postgresql-dev

RUN docker-php-ext-install pdo pdo_pgsql pdo_mysql

RUN apk add php7-mbstring
RUN apk add php7-openssl
RUN apk add php7-tokenizer
RUN apk add php7-xml
RUN apk add php7-xdebug

RUN rm -Rf /var/cache/apk/*
RUN ln -s /usr/bin/php7 /usr/bin/php

RUN curl -sS https://getcomposer.org/installer | php -- \
  --install-dir=/usr/bin --filename=composer

WORKDIR /usr/share/nginx/html