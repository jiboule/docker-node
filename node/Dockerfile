FROM node:latest

MAINTAINER jiboulex

RUN apt-get update
RUN apt-get install vim -y
RUN useradd -ms /bin/bash node
RUN adduser node sudo
RUN echo "fs.inotify.max_user_watches=100000" > /etc/sysctl.conf

#ADD . /var/www
#RUN chown -R node:node /var/www

RUN chown -R node:node /usr/local/lib/node_modules
RUN chown -R node:node /usr/local/bin
RUN chown -R node:node /usr/local/lib

USER node
ENV HOME /var/www

WORKDIR /var/www

EXPOSE 8070 9966
