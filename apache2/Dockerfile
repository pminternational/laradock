FROM webdevops/apache:ubuntu-16.04

MAINTAINER Eric Pfeiffer <computerfr33k@users.noreply.github.com>

ARG PHP_UPSTREAM_CONTAINER=php-fpm
ARG PHP_UPSTREAM_PORT=9000
ARG PHP_UPSTREAM_TIMEOUT=60

ENV WEB_PHP_SOCKET=${PHP_UPSTREAM_CONTAINER}:${PHP_UPSTREAM_PORT}

ENV WEB_DOCUMENT_ROOT=/var/www/

ENV WEB_PHP_TIMEOUT=${PHP_UPSTREAM_TIMEOUT}

EXPOSE 80 443

WORKDIR /var/www/

COPY vhost.conf /etc/apache2/sites-enabled/vhost.conf

ENTRYPOINT ["/opt/docker/bin/entrypoint.sh"]

CMD ["supervisord"]

#FROM webdevops/apache:ubuntu-16.04

#$MAINTAINER Eric Pfeiffer <computerfr33k@users.noreply.github.com>

#RUN apt-get update
#RUN apt-get install -y software-properties-common
#RUN add-apt-repository ppa:ondrej/php
#RUN apt-get update
#RUN apt-get install -y libapache2-mod-php5.6

#ARG PHP_UPSTREAM_CONTAINER=php-fpm
#ARG PHP_UPSTREAM_PORT=9000

#ENV WEB_PHP_SOCKET=${PHP_UPSTREAM_CONTAINER}:${PHP_UPSTREAM_PORT}

#ENV WEB_DOCUMENT_ROOT=/var/www/public/

#EXPOSE 80 443

#WORKDIR /var/www/public/

#COPY vhost.conf /etc/apache2/sites-enabled/vhost.conf

#ENTRYPOINT ["/opt/docker/bin/entrypoint.sh"]

#CMD ["supervisord"]