FROM php:8.1-cli

LABEL maintainer="tim.spiekerkoetter@hdnet.de, thomas.cieslar@hdnet.de"

RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash - && \
    apt-get update && \
    apt-get install -y unzip rsync nodejs git ssh libfreetype6-dev libjpeg62-turbo-dev libpng-dev libgmp-dev libzip-dev && \
    npm i -g npm@8 && \
    docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install -j$(nproc) gd gmp zip mysqli && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /var/www
