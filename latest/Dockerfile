FROM php:7.1.6-apache

# installing some composer
RUN mkdir -p /usr/local/bin/composer
WORKDIR /usr/local/bin/composer

RUN /usr/local/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/bin/php
ENV PATH $PATH:/usr/local/bin:/usr/local/bin/composer

# installing some composer packages
WORKDIR /var/www/html
RUN /usr/local/bin/php /usr/local/bin/composer/composer.phar create-project ec-cube/ec-cube ec-cube "^3.0"

VOLUME /var/www/html