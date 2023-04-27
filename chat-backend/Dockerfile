FROM php:8.1.9-fpm-alpine

ARG TZ=UTC
ENV TZ=Asia/Yangon

RUN apk add --no-cache \
    curl \
    libzip-dev \
    oniguruma-dev \
    unzip

COPY composer.json composer.lock /app/
COPY /tests/* /app/tests/

WORKDIR /app

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php composer-setup.php --install-dir=/usr/local/bin --filename=composer && \
    rm composer-setup.php
    
RUN composer install

RUN rm -rf *

WORKDIR /var/www/html
