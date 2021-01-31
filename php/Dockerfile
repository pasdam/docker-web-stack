FROM php:8.0.1-fpm-alpine3.13

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
