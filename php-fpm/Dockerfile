FROM php:fpm

MAINTAINER Personal App Team

RUN apt-get update && apt-get install -y \
    git \
    unzip \
    xvfb \
    mysql-client


# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

# Set timezone
RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime
RUN "date"

# Type docker-php-ext-install to see available extensions
RUN docker-php-ext-install pdo pdo_mysql

RUN echo 'alias sf="php bin/console"' >> ~/.bashrc

WORKDIR /var/www/sf-semanticui.dev