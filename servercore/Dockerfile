
#  docker build -t cgfootman/heroes:core -f servercore/Dockerfile .
#  docker run -d -p 80:80 --name heroescore cgfootman/heroes:core
#  docker push cgfootman/heroes:core

FROM microsoft/aspnet
MAINTAINER Chris Gibson <cgfootman@hotmail.com>
SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

RUN Remove-Website 'Default Web Site';


RUN mkdir C:\site
# RUN Enable-WindowsOptionalFeature -Online -FeatureName Install-WindowsFeature WEB-ASP,Web-Asp-Net45 

RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "Heroes" -PhysicalPath C:\site -BindingInformation "*:80:"

EXPOSE 80
ADD Site/ /site



