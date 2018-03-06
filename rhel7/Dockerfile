#  docker build -t cgfootman/heroes:rhel7 -f rhel7/Dockerfile .
#  docker run -d -p 80:80 --name heroesrhel7 cgfootman/heroes:rhel7
#  docker push cgfootman/heroes:rhel7

FROM registry.access.redhat.com/dotnet/dotnet-20-rhel7
MAINTAINER Chris Gibson "cgfootman@hotmail.com" 

RUN su yum install epel-release
RUN su yum install nginx
RUN mkdir -p /var/www/html 
ADD rhel7/nginx/global.conf /etc/nginx/conf.d/ 
ADD rhel7/nginx/nginx.conf /etc/nginx/nginx.conf 
Add Site/  /var/www/html/website
EXPOSE 80

# From Nginx container

RUN ln -sf /dev/stdout /var/log/nginx/access.log

RUN ln -sf /dev/stderr /var/log/nginx/error.log

CMD ["nginx", "-g", "daemon off;"]



