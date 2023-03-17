FROM php:8.1-fpm

ARG TZ=UTC
ENV TZ ${TZ}

RUN apt-get update && \
    apt-get install -y git curl unzip libzip-dev libicu-dev libonig-dev && \
    docker-php-ext-install intl pdo_mysql zip bcmath && \
    curl -sL https://deb.nodesource.com/setup_18.x | bash && \
    apt-get install -y nodejs

COPY ./php.ini /usr/local/etc/php/php.ini

COPY --from=composer:2.5.4 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/application

