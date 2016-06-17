FROM php:fpm

MAINTAINER Alexandre JARDIN <aja@emakina.fr>

COPY extra/*.ini /usr/local/etc/php/conf.d/

RUN apt-get update \
    && apt-get install -y git libicu-dev libzip-dev \
    && docker-php-ext-configure opcache --enable-opcache \
    && docker-php-ext-install intl opcache pdo_mysql zip \
    && pecl install xdebug

RUN usermod -u 1000 www-data
