#  docker build -t cgfootman/heroes:apache -f linux/Dockerfile .
#  docker run -d -p 80:80 --name heroesapache cgfootman/heroes:apache
#  docker push cgfootman/heroes:apache



FROM ubuntu:16.04
MAINTAINER Chris Gibson <cgfootman@hotmail.com>
RUN apt-get update && apt-get install -y openssh-server apache2 supervisor
RUN mkdir -p /var/lock/apache2 /var/run/apache2 /var/run/sshd /var/log/supervisor
RUN /usr/local/apache2/conf/
ONBUILD COPY linux/supervisord.conf /etc/supervisor/conf.d/supervisord.conf
ONBUILD COPY Site/ /var/www/html/
EXPOSE 22 80
CMD ["/usr/bin/supervisord"]


