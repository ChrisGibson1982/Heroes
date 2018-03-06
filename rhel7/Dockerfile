#  docker build -t cgfootman/heroes:rhel7 -f rhel7/Dockerfile .
#  docker run -d -p 80:80 --name heroesrhel7 cgfootman/heroes:rhel7
#  docker push cgfootman/heroes:rhel7

FROM registry.access.redhat.com/dotnet/dotnet-20-rhel7
MAINTAINER Chris Gibson "cgfootman@hotmail.com" 

USER root

EXPOSE 80

RUN yum -y update && \
    yum -y install epel-release && \
    yum -y install nginx git logrotate && \
    yum clean all 

ADD centos/nginx/global.conf /etc/nginx/conf.d/ 
ADD centos/nginx/nginx.conf /etc/nginx/nginx.conf 

Add Site/  /var/www/html/website

RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx", "-g", "daemon off;"]



