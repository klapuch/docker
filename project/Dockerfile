FROM php:7.1-apache
RUN echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && echo "cs_CZ.UTF-8 UTF-8" >> /etc/locale.gen
RUN apt-get update && apt-get install -y git locales apt-transport-https \
	&& apt-get install -y libmcrypt-dev && docker-php-ext-install mcrypt \
	&& apt-get install -y libpq-dev && docker-php-ext-install pdo_pgsql \
	&& apt-get install -y zip unzip && docker-php-ext-install zip \
	&& apt-get install -y libxslt-dev && docker-php-ext-install xsl dom
RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer
RUN a2enmod rewrite
RUN service apache2 restart

RUN curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash - \
	&& apt-get install -y nodejs \
	&& ln -sf /usr/bin/nodejs /usr/bin/node
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
	&& echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list \
	&& apt-get update && apt-get install yarn
RUN apt-get clean
