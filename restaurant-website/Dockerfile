# Créer un Dockerfile pour cette application en mode production
FROM php:8.3-fpm
RUN docker-php-source extract \
	&& docker-php-source delete
RUN docker pull nginx