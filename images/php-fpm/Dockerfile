FROM php:5.6-fpm
MAINTAINER Niko Sams <ns@vivid-planet.com>

RUN docker-php-ext-install pdo pdo_mysql

RUN apt-get update && apt-get install -y zlib1g-dev
RUN pecl install memcache \
    && docker-php-ext-enable memcache

RUN apt-get update && apt-get install -y libtidy-dev
RUN docker-php-ext-install tidy

RUN pecl install apcu-4.0.11 \
    && docker-php-ext-enable apcu

ADD ./php.ini /usr/local/etc/php/conf.d
