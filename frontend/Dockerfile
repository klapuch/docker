FROM debian:jessie

RUN apt-get update

RUN apt-get install -y sudo curl apt-transport-https

RUN curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
RUN apt-get install -y nodejs
RUN ln -sf /usr/bin/nodejs /usr/bin/node

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
RUN apt-get update && apt-get install yarn

RUN yarn install
RUN yarn global add less
RUN yarn global add gulp

RUN apt-get clean
