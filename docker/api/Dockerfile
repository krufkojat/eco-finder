FROM php:8.4-fpm-alpine

RUN apk update
RUN apk add build-base git unzip postgresql-dev libzip-dev oniguruma-dev
RUN docker-php-ext-install pdo pdo_mysql pdo_pgsql zip

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html

COPY composer.json composer.lock ./

RUN composer install --no-scripts --no-autoloader --optimize-autoloader

COPY . .

RUN chown -R www-data:www-data /var/www/html

EXPOSE 9000

CMD ["php-fpm"]


