FROM php:7.1

RUN apt-get update

RUN apt-get install -y sudo git

RUN apt-get install -y libmcrypt-dev && docker-php-ext-install mcrypt
RUN apt-get install -y libcurl4-openssl-dev && docker-php-ext-install curl
RUN apt-get install -y libpq-dev && docker-php-ext-install pdo pdo_pgsql
RUN apt-get install -y zip unzip && docker-php-ext-install zip

RUN echo -e "en_US.UTF-8 UTF-8\ncs_CZ.UTF-8 UTF-8" > /etc/locale.gen
RUN apt-get install locales

RUN apt-get clean

RUN docker-php-ext-install mbstring
RUN docker-php-ext-install opcache
RUN docker-php-ext-install json
RUN docker-php-ext-install gettext


RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer
