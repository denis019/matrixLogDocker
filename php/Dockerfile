FROM php:7.2-fpm
WORKDIR /var/www/matrix-log
EXPOSE 9000

RUN apt-get update \
    && pecl install xdebug-2.6.0 \
    && docker-php-ext-enable xdebug \
    && apt-get install -y zip unzip \
    && pecl install mongodb \
    && docker-php-ext-enable mongodb

RUN curl --silent --show-error https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer

RUN echo 'xdebug.remote_enable=1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini
RUN echo 'xdebug.remote_autostart=1' >> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini