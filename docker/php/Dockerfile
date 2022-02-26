FROM php:7.4-fpm

RUN apt-get update && apt-get install -y \
    git \
    libmcrypt-dev \
    zlib1g-dev \
    libzip-dev \
    libssl-dev

#mcrypt
RUN pecl install mcrypt
RUN docker-php-ext-enable mcrypt

#mcrypt
RUN pecl install zip
RUN docker-php-ext-enable mcrypt

#xdebug
RUN pecl install xdebug
RUN docker-php-ext-enable xdebug
RUN sed -i '1 a xdebug.mode=debug' /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN sed -i '1 a xdebug.client_port =9000' /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN sed -i '1 a xdebug.discover_client_host=1' /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

#oauth
RUN apt-get install -y libpcre3 libpcre3-dev
RUN pecl install oauth
RUN docker-php-ext-enable oauth

WORKDIR /app
