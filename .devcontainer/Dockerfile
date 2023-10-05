FROM php:8.2-apache

RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

# RUN pecl install redis-5.3.7 \
# 	&& pecl install xdebug-3.2.1 \
# 	&& docker-php-ext-enable redis xdebug

RUN docker-php-ext-install mysqli pdo pdo_mysql

RUN a2enmod rewrite
