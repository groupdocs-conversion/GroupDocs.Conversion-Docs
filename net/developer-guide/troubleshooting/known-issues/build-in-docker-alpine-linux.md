---
id: build-in-docker-alpine-linux
url: conversion/net/build-in-docker-alpine-linux
title: How to build in docker Alpine Linux
weight: 8
description: "This is a guide about build an web api which uses GroupDocs.Conversion for .NET in a docker container with Alpine Linux"
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---

## Build web api project with GroupDocs.Conversion in Docker

To build an web api which is using GroupDocs.Conversion for .NET in docker container with Alpine Linux use this sample Docker file:

```docker
FROM mcr.microsoft.com/dotnet/aspnet:6.0-alpine AS base
WORKDIR /app
EXPOSE 80
ENV DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=false

RUN apk add --no-cache icu-libs krb5-libs libgcc libintl libssl1.1 libstdc++ zlib
RUN apk add --no-cache ffmpeg libgdiplus

RUN apk add --no-cache msttcorefonts-installer fontconfig
RUN update-ms-fonts && fc-cache fc-cache -f

FROM mcr.microsoft.com/dotnet/sdk:6.0-alpine AS build
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
ENV DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=false

RUN apk add --no-cache icu-libs krb5-libs libgcc libintl libssl1.1 libstdc++ zlib
RUN apk add --no-cache ffmpeg libgdiplus

RUN apk add --no-cache msttcorefonts-installer fontconfig
RUN update-ms-fonts && fc-cache fc-cache -f
```

Also please do not forget to add runtimeconfig.template.json file next to your project file with the following content:

```json
{
    "configProperties": {
        "System.Drawing.EnableUnixSupport": true,
    }
}
```

This will prevent exception "The type initializer for `gdip` throws exception". To learn more about this [read here](https://docs.microsoft.com/en-us/dotnet/core/compatibility/core-libraries/6.0/system-drawing-common-windows-only).