---
id: build-in-docker
url: conversion/net/build-in-docker
title: How to build in docker
weight: 7
description: "This is a guide about build an web api which uses GroupDocs.Conversion for .NET in a docker container"
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

## Build web api project with GroupDocs.Conversion in Docker

To build an web api which is using GroupDocs.Conversion for .NET in docker container use this sample Docker file:

```docker
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

RUN apt-get update && apt-get install -y ffmpeg libgdiplus

RUN apt-get update; apt-get install -y ttf-mscorefonts-installer fontconfig
RUN fc-cache -f -v

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["YourApi/YourApi.csproj", "TestApi/"]
RUN dotnet restore "YourApi/YourApi.csproj"
COPY . .
WORKDIR "/src/YourApi"
RUN dotnet build "YourApi.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "YourApi.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "YourApi.dll"]
```

As you can see the process is the same as building a regular web api project in docker. The main difference is the installation of needed libraries which allows GroupDocs.Conversion for .NET to work properly in a docker container:

```docker
RUN apt-get update && apt-get install -y ffmpeg libgdiplus

RUN apt-get update; apt-get install -y ttf-mscorefonts-installer fontconfig
RUN fc-cache -f -v
```

Also please do not forget to add runtimeconfig.template.json file next to your project file with the following content:

```json
{
    "configProperties": {
        "System.Drawing.EnableUnixSupport": true
    }
}
```

This will prevent exception "The type initializer for `gdip` throws exception". To learn more about this [read here](https://docs.microsoft.com/en-us/dotnet/core/compatibility/core-libraries/6.0/system-drawing-common-windows-only).