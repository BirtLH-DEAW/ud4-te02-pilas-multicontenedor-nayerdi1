FROM php:7.4-fpm

RUN docker-php-ext-install mysqli && apt-get update && apt-get install -y git

# Clona el proyecto desde GitHub
RUN git clone https://github.com/deaw-birt/UD4-despliegue-PHP.git /proyecto

# Mover los archivos a la ubicación adecuada en PHP
RUN mv /proyecto/php/index.php /proyecto/php/dwes.css /var/www/html/

EXPOSE 9000