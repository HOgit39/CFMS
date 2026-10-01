FROM php:8.3-apache

RUN apt-get update && apt-get install -y \
    mariadb-client \
    libmariadb-dev \
    && docker-php-ext-install pdo_mysql mysqli

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
RUN composer install

RUN a2enmod rewrite
WORKDIR /var/www/html