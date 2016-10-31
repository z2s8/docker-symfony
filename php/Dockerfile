FROM php:fpm

MAINTAINER Alexandre JARDIN <aja@emakina.fr>

COPY extra/*.ini /usr/local/etc/php/conf.d/

RUN apt-get update \
    && apt-get install -y git libicu-dev libzip-dev \
    && docker-php-ext-configure opcache --enable-opcache \
    && docker-php-ext-install intl opcache pdo_mysql zip \
    && pecl install apcu apcu-bc xdebug \
    && echo "extension=apcu.so" > /usr/local/etc/php/conf.d/apcu.ini \
    && echo "zend_extension=xdebug.so" > /usr/local/etc/php/conf.d/xdebug.ini

RUN apt-get update \
    && apt-get install -y nodejs npm \
    && ln -s /usr/bin/nodejs /usr/local/bin/node \
    && ln -s /usr/bin/npm /usr/local/bin/npm \
    && npm install -g forever

RUN usermod -u 1000 www-data
