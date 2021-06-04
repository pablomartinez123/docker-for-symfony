FROM nginx:1.17.6-alpine

RUN mkdir /var/www

RUN mkdir /var/www/public

RUN touch /var/www/public/index.php

COPY default.conf /etc/nginx/conf.d/default.conf
