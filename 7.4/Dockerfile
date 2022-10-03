FROM php:7.4-fpm-alpine

RUN wget https://raw.githubusercontent.com/composer/getcomposer.org/76a7060ccb93902cd7576b67264ad91c8a2700e2/web/installer -O - -q | php -- --quiet && \
    mv composer.phar /usr/local/bin/composer && \
    cp $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini
RUN set -e && \
    apk update && apk upgrade && \
    apk add --no-cache icu zlib libpng libjpeg-turbo libwebp libxpm freetype icu-dev zlib-dev libpng-dev jpeg-dev libjpeg-turbo-dev libwebp-dev libxpm-dev freetype-dev && \
    docker-php-ext-configure intl && \
    docker-php-ext-configure gd --with-jpeg --with-webp --with-xpm --with-freetype && \
    docker-php-ext-install intl mysqli gd && \
    apk del icu-dev zlib-dev libpng-dev jpeg-dev libjpeg-turbo-dev libwebp-dev libxpm-dev freetype-dev && \
    echo "Done"

