FROM php:7.3.7-fpm-alpine3.10
RUN apk add icu icu-dev && docker-php-ext-install -j$(nproc) intl
WORKDIR /usr/local/etc/php-fpm.d
# RUN sed -ie "s/listen = .*/listen = \/var\/run\/php-fpm\/php-fpm\.sock/" www.conf
RUN sed -ie "s/listen = .*/listen = 0\.0\.0\.0:9000/" www.conf
RUN sed -ie "s/;listen\.owner = www-data/listen\.owner = nginx/" www.conf && \
    sed -ie "s/;listen\.group = www-data/listen\.group = nginx/" www.conf && \
    sed -ie "s/;listen.mode = 0660/listen.mode = 0750/" www.conf