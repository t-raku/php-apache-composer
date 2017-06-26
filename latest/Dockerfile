FROM php:7.1.6-apache

# RUN docker-php-source extract \
#     && docker-php-ext-configure zip --with-zlib-dir=/usr/src/php/ext/zlib \
#     && docker-php-ext-install -j$(nproc) zip \
# && docker-php-source delete

RUN docker-php-ext-configure zip --with-libzip-dir=/usr/bin/libzip \
&& docker-php-ext-install -j$(nproc) zip

# installing some composer
RUN mkdir -p /usr/local/bin/composer
WORKDIR /usr/local/bin/composer

RUN /usr/local/bin/php -r "readfile('https://getcomposer.org/installer');" | /usr/local/bin/php
ENV PATH $PATH:/usr/local/bin:/usr/local/bin/composer

# installing some composer packages
WORKDIR /var/www/html

VOLUME /var/www/html