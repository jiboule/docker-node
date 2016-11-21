FROM node:latest

MAINTAINER jiboulex

RUN \
    apt-get update && \
    apt-get install -y \
    vim && \
    apt-get clean

RUN useradd -ms /bin/bash node
RUN adduser node sudo
RUN echo "fs.inotify.max_user_watches=100000" > /etc/sysctl.conf

RUN chown -R node:node /usr/local/lib/node_modules
RUN chown -R node:node /usr/local/bin
RUN chown -R node:node /usr/local/lib

USER node
ENV HOME /var/www

WORKDIR /var/www

RUN npm completion >> ~/.bashrc

EXPOSE 8070 9966
