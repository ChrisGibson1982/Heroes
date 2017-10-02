FROM ubuntu: 16.04 
MAINTAINER Chris Gibson "cgfootman@hotmail.com" 

RUN apt-get -y -q update && apt-get -y -q install nginx RUN mkdir -p /var/ www/ html 
ADD linux/nginx/ global.conf /etc/ nginx/ conf.d/ 
ADD linux/nginx/ nginx.conf /etc/ nginx/ nginx.conf 
Add Site/  /var/www/html/website
EXPOSE 80


