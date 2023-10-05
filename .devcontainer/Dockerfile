FROM php:8.2-apache

RUN apt-get update \
    && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y mariadb-client \
    && apt-get install -y sendmail \
    && apt-get install -y libpng-dev \
    && apt-get install -y libzip-dev \
    && apt-get install -y zlib1g-dev \
    && apt-get install -y libonig-dev \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN apache2ctl start

# RUN pecl install redis-5.3.7 \
# 	&& pecl install xdebug-3.2.1 \
# 	&& docker-php-ext-enable redis xdebug

RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN docker-php-ext-install mbstring
# RUN docker-php-ext-install mbmath
RUN docker-php-ext-install zip
RUN docker-php-ext-install gd

RUN a2enmod rewrite
