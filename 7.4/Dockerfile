FROM php:7.4-fpm-alpine

RUN wget https://raw.githubusercontent.com/composer/getcomposer.org/76a7060ccb93902cd7576b67264ad91c8a2700e2/web/installer -O - -q | php -- --quiet && \
    mv composer.phar /usr/local/bin/composer && \
    cp $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini && \
    apk add icu-dev && \
    docker-php-ext-configure intl && \
    docker-php-ext-install intl
