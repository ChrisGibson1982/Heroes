#
#  docker build -t cgfootman/heroes:centos -f centos/Dockerfile .
#  docker run -d -p 80:80 --name heroescentos cgfootman/heroes:centos 
#  docker push cgfootman/heroes:centos 

FROM centos:latest
MAINTAINER Chris Gibson "cgfootman@hotmail.com" 

EXPOSE 80

# RUN adduser hero && usermod -aG wheel hero

RUN yum -y update && \
    yum -y install epel-release && \
    yum -y install nginx git logrotate && \
    yum clean all 
ADD centos/nginx/global.conf /etc/nginx/conf.d/ 
ADD centos/nginx/nginx.conf /etc/nginx/nginx.conf 
Add Site/  /var/www/html/website

RUN ln -sf /dev/stdout /var/log/nginx/access.log

RUN ln -sf /dev/stderr /var/log/nginx/error.log


RUN  && chmod -R 777 /var/log/nginx /var/cache/nginx/ \
     && chmod 644 /etc/nginx/*

CMD ["nginx", "-g", "daemon off;"]

# CMD ["su", "-", "hero", "-c", "nginx", "-g", "daemon off;"]

