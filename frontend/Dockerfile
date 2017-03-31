FROM debian:jessie

RUN apt-get update && apt-get install -y sudo curl apt-transport-https

RUN curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash - \
	&& apt-get install -y nodejs \
	&& ln -sf /usr/bin/nodejs /usr/bin/node

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
	&& echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list \
	&& apt-get update && apt-get install yarn \
	&& yarn install \
	&& yarn global add less \
	&& yarn global add gulp \
	&& apt-get clean
