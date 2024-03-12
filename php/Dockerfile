# FROM php:8.0-apache

# RUN apt update \
#     && apt install -y \
#     g++ \
#     libicu-dev \
#     libpq-dev \
#     libzip-dev \
#     zip \
#     zlib1g-dev \
#     && docker-php-ext-install \
#     intl \
#     opcache \
#     pdo \
#     pdo_pgsql \
#     pgsql \

#     WORKDIR /var/www/everlasting-heaven-suite

# RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


# # just added
# RUN mkdir -p /var/www/html/everlasting-heaven-suite/
# COPY . /var/www/html/everlasting-heaven-suite/
# RUN chown -R www-data:www-data /var/www/html/everlasting-heaven-suite

# -----------------

# Dockerfile
FROM php:7.2-cli

RUN apt-get update -y && apt-get install -y libmcrypt-dev

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN docker-php-ext-install pdo mbstring

WORKDIR /app
COPY . /app

RUN composer install

EXPOSE 8000
CMD php artisan serve --host=0.0.0.0 --port=8000