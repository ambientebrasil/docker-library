FROM ubuntu:20.04
RUN apt-get update && apt-get install -y nano wget unzip logrotate mysql-client curl
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y apache2 \
    && chown -R www-data:www-data /var/www/
RUN apt-get install -y php7.4 composer
RUN apt-get install -y php7.4-curl php7.4-gd php7.4-imagick php7.4-xml php7.4-zip php7.4-mysql
RUN a2enmod rewrite headers
WORKDIR /var/www/html
EXPOSE 80