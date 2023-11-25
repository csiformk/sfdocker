FROM php:8.2-fpm-alpine

RUN apk --no-cache --update add \
vim \
git \
curl \
zip \
sqlite \
unzip \
bash

# Git
RUN git config --global user.email "" ; git config --global user.name "sfgituser"

RUN docker-php-ext-install pdo pdo_mysql

# Composer
RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" ; php -r "if (hash_file('sha384', 'composer-setup.php') === 'e21205b207c3ff031906575712edab6f13eb0b361f2085f1f1237b7126d785e826a450292b6cfd1d64d92e6563bbde02') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" ; php composer-setup.php ; php -r "unlink('composer-setup.php');" ; mv composer.phar /usr/local/bin/composer

# Symfony cli
RUN curl -1sLf 'https://dl.cloudsmith.io/public/symfony/stable/setup.alpine.sh' | bash ; apk add symfony-cli

WORKDIR /var/www
