FROM ubuntu:20.04
RUN apt-get update && apt-get install -y nano wget unzip logrotate mysql-client curl
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y apache2 \
    && chown -R www-data:www-data /var/www/
RUN apt-get install -y php7.4 composer
RUN apt-get install -y php7.4-curl php7.4-gd php7.4-imagick php7.4-xml php7.4-zip php7.4-mysql
RUN a2enmod rewrite headers
RUN apt install -y php-xdebug \
    && echo "[Xdebug]" >> /etc/php/7.4/apache2/php.ini \
    && echo "zend_extension=$(find /usr/ -name xdebug.so)" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.remote_enable=on" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.remote_handler=dbgp" >>  /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.remote_port=9000" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.remote_autostart=on" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.remote_connect_back=on" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.idekey=docker" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.remote_log=/var/log/xdebug.log" >> /etc/php/7.4/apache2/php.ini \
    && echo "xdebug.default_enable=on" >> /etc/php/7.4/apache2/php.ini
EXPOSE 80