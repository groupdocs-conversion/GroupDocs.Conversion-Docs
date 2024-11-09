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

- [Python 3.9](https://www.python.org/downloads/) or above.
- [.NET 6.0](https://dotnet.microsoft.com/en-us/download/dotnet/6.0) runtime or above.

## Supported Operating Systems

### Windows

- Microsoft Windows 11 (x64)
- Microsoft Windows 10 (x64, x86)
- Microsoft Windows 7, 8, 8.1 (x64, x86)
- Microsoft Windows Vista (x64, x86)
- Microsoft Windows XP (x64, x86)
- Microsoft Windows Server 2003 and later

### macOS

GroupDocs.Conversion for Python via .NET supports macOS running on both Intel and Apple Silicon processors.

Supported versions:

- macOS Sequoia (version 15)
- macOS Sonoma (version 14)
- macOS Ventura (version 13)
- macOS Monterey (version 12)
- macOS Big Sur (version 11)
- macOS Catalina (version 10.15)
- macOS Mojave (version 10.14)

## Additional System Libraries

### macOS System Requirements

GroupDocs.Conversion for Python via .NET partially relies on `libgdiplus` for converting images or documents that contain images. The library is required for such conversions and can be installed using the [Homebrew](https://brew.sh/) package manager:

```ps
brew install mono-libgdiplus
```

Ensure `libgdiplus` is installed if you encounter issues with image-based conversions.
