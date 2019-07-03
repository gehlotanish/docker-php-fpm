FROM php:7.3-fpm


RUN apt-get -y update --fix-missing
RUN apt-get upgrade -y

# Install useful tools
RUN apt-get -y install apt-utils nano wget dialog

# Install important libraries
RUN apt-get -y install --fix-missing apt-utils build-essential htop git curl libcurl3 libcurl3-dev zip

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer


# Install xdebug
RUN pecl install xdebug-2.7.1
RUN docker-php-ext-enable xdebug

# Install redis
RUN pecl install redis-4.0.1
RUN docker-php-ext-enable redis

# Other PHP7 Extensions


RUN apt-get -y install libsqlite3-dev libsqlite3-0 mysql-client
RUN docker-php-ext-install pdo_mysql 
RUN docker-php-ext-install pdo_sqlite
RUN docker-php-ext-install mysqli

RUN docker-php-ext-install curl
RUN docker-php-ext-install tokenizer
RUN docker-php-ext-install json

RUN apt-get -y install zlib1g-dev libzip-dev
RUN docker-php-ext-install zip

RUN apt-get -y install libicu-dev
RUN docker-php-ext-install -j$(nproc) intl

RUN apt-get -y  install openssl
RUN docker-php-ext-install mbstring

RUN apt-get -y install libssl-dev
RUN docker-php-ext-install phar
RUN docker-php-ext-install bcmath

RUN apt-get -y install  libbz2-dev
RUN docker-php-ext-install bz2

RUN apt-get -y install libxml2 libxml2-dev
RUN docker-php-ext-install posix
RUN docker-php-ext-install soap

RUN docker-php-ext-install sockets

RUN docker-php-ext-install xml
RUN docker-php-ext-install xmlrpc
RUN docker-php-ext-install xmlwriter

RUN apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev
RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ 
RUN docker-php-ext-install -j$(nproc) gd


RUN rm -rf /var/lib/apt/lists/*

