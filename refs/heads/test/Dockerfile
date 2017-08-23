from microsoft/aspnetcore-build:lts
#RUN echo $VERSION
#ARG VERSION=latest2
#RUN echo $VERSION
#
#RUN echo $VERSION > image_version
#
##COPY ./WebApplication1 /app
##ARG source
#WORKDIR /app
##COPY ${source:-obj} .
#RUN cat PATH
#
##RUN ["dotnet", "restore"]
##RUN ["dotnet", "build"]
ARG source
WORKDIR /app
EXPOSE 80
COPY . .

RUN ["dotnet", "restore"]
RUN ["dotnet", "build"]
RUN ["dotnet", "publish","-c","Release","-o","bin/Publish"]
#RUN ["ls"]
#RUN ["ls","bin/Release/netcoreapp1.1"]
#RUN ["ls","obj/Release/netcoreapp1.1"]
#RUN ["ls","/app/bin/Release/netcoreapp1.1/"]

ENTRYPOINT ["dotnet", "bin/Publish/WebApplication1.dll"]
