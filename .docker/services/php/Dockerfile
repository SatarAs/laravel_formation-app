FROM php:8.1-fpm-alpine

RUN apk add --update nodejs npm yarn && apk --no-cache add bash git

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/
RUN docker-php-ext-install mysqli && \
    docker-php-ext-install pdo_mysql
RUN chmod +x /usr/local/bin/install-php-extensions

RUN apk add --no-cache \
    coreutils \
    gettext \
    php8-fpm \
    php8-ctype \
    php8-curl \
    php8-dom \
    php8-gd \
    php8-iconv \
    php8-json \
    php8-intl \
    php8-fileinfo\
    php8-mbstring \
    php8-opcache \
    php8-openssl \
    php8-pdo \
    php8-pdo_mysql \
    php8-mysqli \
    php8-xml \
    php8-xsl \
    php8-zlib \
    php8-phar \
    php8-tokenizer \
    php8-session \
    php8-simplexml \
    php8-zip \
    php8-xmlwriter \
    php8-sodium \
    php8-pecl-apcu \
    make \
    curl

RUN wget https://getcomposer.org/installer -O - | php -- --install-dir=/usr/local/bin --filename=composer


ADD php.ini /usr/local/etc/php/php.ini
ADD php-fpm.conf /etc/php/php-fpm.d/

WORKDIR /var/www/laravel_formation

EXPOSE 9000

CMD ["php-fpm", "-F"]
