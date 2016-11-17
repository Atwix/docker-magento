FROM php:5.6-fpm

RUN apt-get -qq update && apt-get -qq install libxml++2.6-dev > /dev/null
RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng12-dev \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd mbstring mysql mysqli pdo pdo_mysql soap
    
RUN apt-get install -y libmcrypt-dev
RUN docker-php-ext-install mcrypt

RUN apt-get install -y libicu-dev
RUN pecl install intl
RUN docker-php-ext-install intl