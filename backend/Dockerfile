# Use a imagem PHP Alpine 3.18 como base
FROM php:8.1-alpine3.18

# Instale as dependências necessárias
RUN apk add --no-cache \
    build-base \
    libpng-dev \
    libjpeg-turbo-dev \
    libwebp-dev \
    zlib-dev \
    libxpm-dev \
    freetype-dev \
    libzip-dev \
    icu-dev \
    oniguruma-dev \
    unzip \
    libpq-dev

RUN docker-php-ext-install pdo_pgsql pgsql

# Instale o Composer globalmente
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Defina o diretório de trabalho dentro do contêiner
WORKDIR /var/www/html