FROM debian:jessie

RUN apt-get update

RUN apt-get install -y sudo curl
RUN curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
RUN apt-get install -y nodejs
RUN ln -sf /usr/bin/nodejs /usr/bin/node
RUN npm cache clean -f && npm install -g n && n stable
RUN npm install -g less
RUN npm install -g gulp

RUN apt-get clean
