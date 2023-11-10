FROM php:fpm-alpine AS phpbase

RUN apk add icu-dev

RUN docker-php-ext-install mysqli pdo pdo_mysql \
    && docker-php-ext-enable mysqli \
    && docker-php-ext-enable pdo \
    && docker-php-ext-enable pdo_mysql \
    && docker-php-ext-configure intl && docker-php-ext-install intl \
    && docker-php-ext-configure pcntl --enable-pcntl \
    && docker-php-ext-install pcntl

# COPY ./app/ /app

WORKDIR /app

RUN chmod -R 0777 ./cache ./feed-icons ./lock

# RUN chmod u+x /app/start.sh

# RUN adduser -D ttrss

# USER ttrss

#CMD ["/bin/sh", "start.sh", $container_name]
# ENTRYPOINT ["/app/start.sh"]
# RUN /app/start.sh