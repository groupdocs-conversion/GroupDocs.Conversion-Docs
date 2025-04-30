---
id: installation-linux
url: conversion/net/installation-linux
title: Install GroupDocs.Conversion for .NET on Linux
linkTitle: Linux Installation
weight: 5
description: "Step-by-step guide to install and run GroupDocs.Conversion for .NET on Linux"
keywords:
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---

This article explains how to install and run **GroupDocs.Conversion for .NET** on a Linux-based system using .NET Core or .NET 5/6+. It also includes instructions for installing native dependencies that might be required when running in a headless environment.

## Prerequisites

Ensure the following tools and packages are installed:

- .NET 6.0 SDK or later: [Install .NET on Linux](https://learn.microsoft.com/en-us/dotnet/core/install/linux)
- A Linux distribution such as Ubuntu, Debian, CentOS, or Alpine
- `libgdiplus`, `fontconfig`, and basic font packages

To install the required packages:

### Ubuntu / Debian:

```bash
sudo apt update
sudo apt install -y libgdiplus fontconfig ttf-mscorefonts-installer
```

### CentOS / RHEL:

```bash
sudo yum install -y epel-release
sudo yum install -y libgdiplus fontconfig msttcore-fonts-installer cabextract
```

### Alpine (Minimal Docker / Linux Distros):

```bash
apk add --no-cache libgdiplus fontconfig ttf-dejavu
```

> If using Alpine with Docker, check the [Build in Docker - Alpine Linux](https://docs-qa.groupdocs.com/conversion/net/build-in-docker-alpine-linux/) article.

## Install GroupDocs.Conversion using .NET CLI

In your project directory, run:

```bash
dotnet add package GroupDocs.Conversion
```

To restore packages:

```bash
dotnet restore
```

## Run Your Project

After adding the package and restoring dependencies, build and run your application:

```bash
dotnet run
```

## Headless Environments (Optional Fonts Setup)

In Linux containers or headless setups, fonts may be missing. You can install or configure them as follows:

```bash
sudo apt install -y fonts-dejavu ttf-mscorefonts-installer
```

Or configure custom fonts in code using `FontSettings.SetFontsFolder`.

## Troubleshooting

- If you encounter `System.TypeInitializationException` or `System.DllNotFoundException`, ensure `libgdiplus` is installed.
- If font rendering is broken or content is missing, install system fonts or configure a custom font folder.

---

For Docker setups, see:

- [Build in Docker](https://docs-qa.groupdocs.com/conversion/net/build-in-docker/)
- [Build in Docker - Alpine Linux](https://docs-qa.groupdocs.com/conversion/net/build-in-docker-alpine-linux/)
