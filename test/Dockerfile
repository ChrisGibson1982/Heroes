#  docker build -rm -t cgfootman/heroes:test -f test/Dockerfile .
#  docker run -d -p80:80  --name heroestest cgfootman/heroes:test
#  docker push cgfootman/heroes:test

FROM microsoft/dotnet:nanoserver
WORKDIR /App
EXPOSE 80
COPY WebApp/ .
ENTRYPOINT ["dotnet", "Heroes.dll"]