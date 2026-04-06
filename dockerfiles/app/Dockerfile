FROM php:8.3-fpm

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    git unzip \
    libpq-dev libpng-dev libonig-dev libxml2-dev \
    && docker-php-ext-install pdo_pgsql pgsql mbstring exif pcntl bcmath gd \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

RUN git config --global user.name "Rafael" \
    && git config --global user.email "rafaelddem@gmail.com" 

RUN git clone -b main https://github.com/rafaelddem/desafio_innova_api.git /var/www/html \
    && git config --global --add safe.directory /var/www/html

WORKDIR /var/www/html

RUN composer update --no-dev --optimize-autoloader

RUN cp .env.example .env && php artisan key:generate && php artisan jwt:secret

EXPOSE 8000
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]
