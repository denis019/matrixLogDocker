FROM php:7.2-fpm
EXPOSE 9000
WORKDIR /var/www/matrix-log/MatrixLogPresenter

RUN apt-get update \
    && apt-get install -y zip unzip \
    && apt-get install -y libcurl4-openssl-dev pkg-config libssl-dev \
    && pecl install mongodb \
    && docker-php-ext-enable mongodb

# lumen packages
RUN docker-php-ext-install mbstring tokenizer mysqli pdo_mysql

RUN curl --silent --show-error https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/composer