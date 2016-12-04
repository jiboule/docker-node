FROM php:5.6-apache

MAINTAINER jiboulex

RUN apt-get update && apt-get install -y \
    zlib1g-dev \
    libicu-dev \
    g++ \
    apt-utils \
    vim \
    git \
    wget \
    php5-curl \
    sudo

COPY php.ini /usr/local/etc/php/php.ini
COPY php.ini /etc/php5/apache2/conf.d/php.ini

COPY apache-config.conf /etc/apache2/sites-enabled/000-default.conf

WORKDIR /var/www

RUN a2enmod rewrite

CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]
