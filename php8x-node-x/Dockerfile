ARG php_version=8.2

FROM docker.io/library/php:${php_version}-cli

ARG node_version=lts
ARG npm_version=latest

LABEL maintainer="tim.spiekerkoetter@hdnet.de"

RUN curl -sL "https://deb.nodesource.com/setup_${node_version}.x" | bash - && \
    apt-get update && \
    apt-get install -y unzip rsync nodejs git ssh libfreetype6-dev libjpeg62-turbo-dev libpng-dev libgmp-dev libzip-dev libxml2-dev && \
    npm i -g "npm@${npm_version}" && \
    docker-php-ext-configure gd --with-freetype --with-jpeg && \
    docker-php-ext-install -j$(nproc) gd gmp zip mysqli soap && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /var/www
