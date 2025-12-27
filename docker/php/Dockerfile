FROM php:8.2-fpm

# Dépendances système + bash
RUN apt-get update && apt-get install -y \
    bash \
    git \
    unzip \
    libicu-dev \
    libzip-dev \
    && docker-php-ext-install \
        pdo_mysql \
        intl \
        zip \
    && rm -rf /var/lib/apt/lists/*

# Installer Composer
COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
