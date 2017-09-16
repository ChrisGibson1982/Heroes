
#  docker build -rm -t cgfootman/heroes:core -f servercore/Dockerfile .
#  docker run -d -p 80:80 --name heroescore cgfootman/heroes:core
#  docker push cgfootman/heroes:core

FROM microsoft/windowsservercore
MAINTAINER Chris Gibson <cgfootman@hotmail.com>
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

ADD servercore/install/ServiceMonitor.exe /ServiceMonitor.exe


RUN powershell -Command Add-WindowsFeature Web-Server

RUN Remove-Website 'Default Web Site';

RUN mkdir C:\site

RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "Heroes" -PhysicalPath C:\site -BindingInformation "*:80:"

ADD Site/ /site

EXPOSE 80

ENTRYPOINT ["C:\\ServiceMonitor.exe", "w3svc"]



