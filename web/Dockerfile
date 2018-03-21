FROM php:5.6-apache

COPY config/php.ini /usr/local/etc/php/

COPY app /var/www/html/

RUN a2enmod rewrite

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install \
    -y --no-install-recommends \
    libjpeg62-turbo-dev \
    libfreetype6-dev \
    git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install zip \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install opcache \
    && docker-php-ext-install mbstring

RUN usermod -u 1000 www-data

WORKDIR /var/www/html/
