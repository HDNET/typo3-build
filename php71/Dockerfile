FROM php:7.1

LABEL maintainer="tim.spiekerkoetter@hdnet.de"

COPY nodejs /etc/apt/preferences.d/nodejs
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash - && \
    apt-get update && \
    apt-get install -y unzip rsync nodejs git ssh && \
    curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    rm -rf /var/lib/apt/lists/*
