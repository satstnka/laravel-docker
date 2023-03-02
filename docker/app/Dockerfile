FROM php:7.4-apache

ADD php.ini /usr/local/etc/php/
ADD 000-default.conf /etc/apache2/sites-enabled/

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
RUN mv composer.phar /usr/bin/

RUN apt-get update
RUN apt-get install -y git zip unzip vim libpng-dev libpq-dev libzip-dev
RUN docker-php-ext-install pdo_mysql zip
