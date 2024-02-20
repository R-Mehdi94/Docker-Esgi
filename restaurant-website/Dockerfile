# Créer un Dockerfile pour cette application en mode production
FROM php:8.3-fpm

WORKDIR /var/www/html

COPY . /var/www/html

ENV COMPOSER_ALLOW_SUPERUSER=1

RUN apt-get update && apt-get install -y \
        libicu-dev \
        libzip-dev \
        zip \
        git \
    && docker-php-ext-install intl zip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN curl -sS https://getcomposer.org/installer | php -- \
     --install-dir=/usr/bin --filename=composer

RUN wget https://get.symfony.com/cli/installer -O - | bash

RUN composer install --no-dev --optimize-autoloader

RUN composer require symfony/runtime

RUN php bin/console asset-map:compile

RUN php bin/console cache:clear --env=prod