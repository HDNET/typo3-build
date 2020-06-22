FROM php:7.4-cli

LABEL maintainer="tim.spiekerkoetter@hdnet.de"

RUN curl -sL https://deb.nodesource.com/setup_12.x | bash - && \
    apt-get update && \
    apt-get install -y unzip rsync nodejs git ssh libfreetype6-dev libjpeg62-turbo-dev libpng-dev libgmp-dev libzip-dev && \
    docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ && \
    docker-php-ext-install -j$(nproc) gd gmp zip && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    rm -rf /var/lib/apt/lists/*

WORKDIR /var/www
