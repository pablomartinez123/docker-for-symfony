FROM php:7.4-fpm-alpine

RUN apk --update --no-cache add git supervisor libxml2-dev
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install opcache
RUN docker-php-ext-install bcmath
RUN apk add --no-cache $PHPIZE_DEPS
RUN pecl install xdebug
#####RUN docker-php-ext-enable xdebug
RUN docker-php-ext-install soap

COPY --from=composer /usr/bin/composer /usr/bin/composer
WORKDIR /var/www

COPY ./docker_api_rebillia/php-fpm/supervisord.conf /etc/supervisord.conf

######RUN echo "172.22.0.4 local.rebillia.com" >> /etc/hosts

RUN mkdir /var/www/public
COPY ./index.php /var/www/public

EXPOSE 9000
