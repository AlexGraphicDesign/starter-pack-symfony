FROM php:8.4.10-apache as php-apache

#dépendances
RUN apt-get update && apt-get install -y zip unzip zlib1g-dev libldb-dev libjpeg62-turbo-dev libzip-dev cron sudo libicu-dev g++ libpng-dev autoconf pkg-config libssl-dev libpq-dev libxslt1-dev ghostscript

# Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
# Cache Composer
RUN chown -R www-data: /var/www

COPY docker/certs/ /usr/local/share/ca-certificates/

#ext PHP
RUN docker-php-ext-configure intl
RUN docker-php-ext-install xsl intl gd zip pdo_mysql
RUN docker-php-ext-enable opcache

RUN pecl install xdebug \
    && docker-php-ext-enable xdebug

COPY docker/app.conf /etc/apache2/sites-available/000-default.conf
COPY docker/custom.ini /usr/local/etc/php/conf.d/custom.ini

COPY docker/local/php/entrypoint.sh /usr/bin/entrypoint.sh

ARG UID=1000
RUN usermod -u ${UID} www-data
RUN chmod +x /usr/bin/entrypoint.sh
CMD ["/usr/bin/entrypoint.sh"]
