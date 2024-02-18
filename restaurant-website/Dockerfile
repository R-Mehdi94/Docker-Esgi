# Créer un Dockerfile pour cette application en mode production
FROM php:8.3-fpm

ENV APP_ENV=prod

EXPOSE 80

ADD --chmod=0755 https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN chmod +x /usr/local/bin/install-php-extensions && install-php-extensions intl && \
    curl -sSL https://getcomposer.org/installer | php -- --disable-tls && \
    apt update && apt install -yqq nodejs npm

RUN curl -sSL https://get.symfony.com/cli/installer | bash

RUN symfony server:start


