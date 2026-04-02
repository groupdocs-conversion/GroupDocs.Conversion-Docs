---
id: system-requirements
url: conversion/python-net/system-requirements
title: System Requirements
weight: 1
description: GroupDocs.Conversion for Python via .NET sustem requirements.
keywords: GroupDocs.Conversion for Python via .NET, Conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: false
toc: true
---

## General Requirements

- [Python](https://www.python.org/downloads/) versions **3.9–3.11** are supported

## Supported Operating Systems

### Windows

* Microsoft Windows 11 (x64)
* Microsoft Windows 10 (x64, x86)
* Microsoft Windows 7, 8, 8.1, Vista, XP (x64, x86)
* Microsoft Windows Server 2003 and later

### Linux and macOS (partial support)

GroupDocs.Conversion include macOS support for Intel and/or Apple Silicon (M-series) processors. Linux packages will be added in future releases.

## Additional System Libraries

### Linux and macOS System Requirements

GroupDocs.Conversion for Python via .NET relies on `libgdiplus` for processing images or documents that contain images. 

#### Linux installation

When using GroupDocs.Conversion in a Linux environment, the following packages should be installed for proper library operation:

1. **libgdiplus** - Mono library providing a GDI+-compatible API on non-Windows operating systems.  
2. **libx11-dev** - Required for drawing functions (image/font rendering).  
3. **fontconfig** - Enables font lookup for text rendering with System.Drawing.  
4. **ttf-mscorefonts-installer** - Provides Microsoft-compatible fonts required by GroupDocs.Total.

To install packages on Debian-based Linux distributions, use [apt-get](https://wiki.debian.org/apt-get):

```bash
sudo apt-get update
sudo apt-get install -y libgdiplus libx11-dev fontconfig ttf-mscorefonts-installer
```

If some packages are not available, you can add the contrib repository:

```bash
RUN sed -i'.bak' 's/$/ contrib/' /etc/apt/sources.list
```

#### macOS installation

The library is required and can be installed using the [Homebrew](https://brew.sh/) package manager:

```ps
brew install mono-libgdiplus
```

Ensure `libgdiplus` is installed if you encounter issues with processing images or documents that contain images.