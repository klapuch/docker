FROM php:7.1

RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && echo "cs_CZ.UTF-8 UTF-8" >> /etc/locale.gen

RUN apt-get update -qq && apt-get install -y git locales libcurl4-openssl-dev \
	&& apt-get install -y libmcrypt-dev && docker-php-ext-install mcrypt \
	&& apt-get install -y libpq-dev && docker-php-ext-install pdo_pgsql \
	&& apt-get install -y zip unzip && docker-php-ext-install zip \
	&& apt-get install -y gettext && docker-php-ext-install gettext \
	&& apt-get clean

RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer
