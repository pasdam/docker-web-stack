FROM php:8.2.8-fpm-alpine3.18

RUN apk update && \
    apk upgrade && \
    docker-php-ext-install mysqli

RUN apk add --no-cache \
        libpng \
        libpng-dev && \
    docker-php-ext-install gd && \
    apk del libpng-dev

RUN apk add --no-cache \
    libzip-dev \
    zip && \
    docker-php-ext-configure zip && \
    docker-php-ext-install zip
