FROM ubuntu:latest

RUN apt-get update && apt-get install -y apache2 git \
    && apt-get -y install libapache2-mod-fcgid \
    && a2enmod proxy_fcgi

# Clona el repositorio desde Github
RUN git clone https://github.com/deaw-birt/UD4-despliegue-PHP.git /proyecto \
#&& mkdir -p /usr/local/apache2/htdocs/php/ \
&& mv /proyecto/php/index.php /proyecto/php/dwes.css var/www/html/ 
#&& cp /usr/local/apache2/htdocs/php/index.php /usr/local/apache2/htdocs/php/dwes.css /var/www/html/ 

COPY 000-default.conf /etc/apache2/sites-available
RUN a2ensite 000-default && service apache2 restart

EXPOSE 80
CMD ["apachectl", "-D", "FOREGROUND"]