FROM php:fpm-alpine

RUN set -ex; \
  apk add --no-cache --virtual .build-deps \
    freetype-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    libzip-dev \
    libmcrypt-dev \
    postgresql-dev \
    tidyhtml-dev \
  ; \
  \ 
  docker-php-ext-configure pgsql \
    -with-pgsql=/usr/include/postgresql/; \
  \
  docker-php-ext-install \
    exif \
    gd \
    opcache \
    pdo \
    pdo_pgsql \
    pgsql \
  ; \
  apk del .build-deps
