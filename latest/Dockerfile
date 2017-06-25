FROM php-zendserver:latest

# installing some composer packages
RUN /usr/local/zend/bin/php composer.phar create-project ec-cube/ec-cube ec-cube "^3.0"

VOLUME /var/www/html