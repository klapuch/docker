FROM php:7.1

RUN apt-get update

RUN apt-get install -y sudo git libcurl4-openssl-dev

RUN apt-get install -y libmcrypt-dev && docker-php-ext-install mcrypt
RUN apt-get install -y libpq-dev && docker-php-ext-install pdo_pgsql
RUN apt-get install -y zip unzip && docker-php-ext-install zip
RUN apt-get install -y gettext && docker-php-ext-install gettext

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen
RUN echo "cs_CZ.UTF-8 UTF-8" >> /etc/locale.gen
RUN apt-get install -y locales

RUN apt-get clean

RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer
