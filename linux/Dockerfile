FROM httpd:2.4
MAINTAINER Chris Gibson <cgfootman@hotmail.com>
USER root

COPY ./public-html/ /usr/local/apache2/htdocs/
COPY Site/ /var/www/

EXPOSE 80


CMD ["-D", "FOREGROUND"]
ENTRYPOINT ["/usr/sbin/httpd"]
