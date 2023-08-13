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
    libpq-dev \
    wget

RUN docker-php-ext-install pdo_pgsql pgsql

# Instale o Composer globalmente
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN wget https://github.com/jwilder/dockerize/releases/download/v0.6.1/dockerize-linux-amd64-v0.6.1.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-v0.6.1.tar.gz \
    && rm dockerize-linux-amd64-v0.6.1.tar.gz

# Defina o diretório de trabalho dentro do contêiner
WORKDIR /var/www/html