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

This article explains how to install and run **GroupDocs.Conversion for .NET** on a Linux-based system using .NET 6+. It also includes instructions for installing native dependencies that might be required when running in a headless environment.

## Prerequisites

Ensure the following tools and packages are installed:

- .NET 6.0 SDK or later: [Install .NET on Linux](https://learn.microsoft.com/en-us/dotnet/core/install/linux)
- A Linux distribution such as Ubuntu, Debian, CentOS/RHEL, or Alpine
- `libgdiplus`, `fontconfig`, and TrueType fonts

## Installing Dependencies

### Ubuntu / Debian

Ensure the multiverse repository is enabled:

```bash
sudo add-apt-repository multiverse
sudo apt update
```

Install the required packages:

```bash
sudo apt install -y libgdiplus fontconfig ttf-mscorefonts-installer
```

> `ttf-mscorefonts-installer` is in the multiverse repository and downloads Microsoft fonts.

### CentOS / RHEL

Enable EPEL repository and install required packages:

```bash
sudo yum install -y epel-release
sudo yum install -y libgdiplus fontconfig cabextract
```

To install Microsoft TrueType fonts:

```bash
wget https://downloads.sourceforge.net/project/mscorefonts2/rpms/msttcore-fonts-installer-2.6-1.noarch.rpm
sudo yum install -y msttcore-fonts-installer-2.6-1.noarch.rpm
```

> Note: This method uses a third-party RPM for Microsoft fonts. You may need `--nogpgcheck` depending on your system configuration.

### Alpine Linux

Install minimal dependencies using `apk`:

```bash
apk add --no-cache libgdiplus fontconfig ttf-dejavu
```

> `ttf-dejavu` provides good font compatibility in Alpine.

## Install GroupDocs.Conversion using .NET CLI

In your project directory:

```bash
dotnet add package GroupDocs.Conversion
dotnet restore
```

## Run Your Project

Build and run your project:

```bash
dotnet run
```

## Optional Fonts Configuration

In container or headless environments, if rendering issues occur, configure custom fonts in code:

```csharp
FontSettings.SetFontsFolder("/path/to/fonts", true);
```

## Troubleshooting

- If you encounter `System.DllNotFoundException`, check if `libgdiplus` is installed.
- If fonts are missing or rendered incorrectly, verify fonts are present and accessible.

---

For Docker-specific environments, see:

- [Build in Docker](https://docs.groupdocs.com/conversion/net/build-in-docker/)
- [Build in Docker - Alpine Linux](https://docs.groupdocs.com/conversion/net/build-in-docker-alpine-linux/)
