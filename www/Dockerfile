FROM ubuntu:18.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update &&  apt-get install -y \
    apache2 \
    libapache2-mod-php \
    libapache2-mod-rpaf \
    php-mysql \
    git \
    php-memcached \
    curl \
    php-cli \
    php-mbstring \
    unzip \
    php-pgsql \
    glusterfs-client \
    nano

RUN a2enmod rpaf
RUN rm /var/www/html/index.html
RUN mkdir /var/www/html/images
ADD code/* /var/www/html/
ADD config.php /var/www/html
ADD init.sh /
EXPOSE 80
ENTRYPOINT ["/init.sh"]







