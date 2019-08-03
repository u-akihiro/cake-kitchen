FROM php:7.3.7-fpm-alpine3.10
RUN apk add icu icu-dev && docker-php-ext-install -j$(nproc) intl