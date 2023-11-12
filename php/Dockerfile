FROM php:fpm-alpine AS phpbase

RUN apk add icu-dev git

RUN docker-php-ext-install mysqli pdo pdo_mysql \
    && docker-php-ext-enable mysqli \
    && docker-php-ext-enable pdo \
    && docker-php-ext-enable pdo_mysql \
    && docker-php-ext-configure intl && docker-php-ext-install intl \
    && docker-php-ext-configure pcntl --enable-pcntl \
    && docker-php-ext-install pcntl

RUN git clone https://git.tt-rss.org/fox/tt-rss.git /app

WORKDIR /app

RUN rm -rf .git

RUN chmod -R 0777 ./cache ./feed-icons ./lock

RUN adduser ttrs --disabled-password 

USER ttrss