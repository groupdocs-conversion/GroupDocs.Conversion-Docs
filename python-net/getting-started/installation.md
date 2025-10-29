---
id: installation
url: conversion/python-net/getting-started/installation
title: Installation
linkTitle: Installation
weight: 1
description: "This guide explains how to install GroupDocs.Conversion for Python via .NET to your environment"
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

## Install Package from PyPI

PyPI (Python Package Index) is a repository of software packages for the Python programming language. Visit the [groupdocs-conversion-net](https://pypi.org/project/groupdocs-conversion-net/) package page for more details. 

### Installing the Package

To install the package, open a terminal and run the following command:

{{< tabs "example1">}}
{{< tab "Windows" >}}
```ps
py -m pip install groupdocs-conversion-net
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m pip install groupdocs-conversion-net
```
{{< /tab >}}
{{< /tabs >}}

When running the command on Windows, you can expect the following output:

```bash
Collecting groupdocs-conversion-net
  Downloading groupdocs_conversion_net-*24.12-py3-none-win_amd64*.whl.metadata (6.8 kB)
  Downloading groupdocs_conversion_net-24.12-py3-none-win_amd64.whl (220.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 220.3/220.3 MB 2.8 MB/s eta 0:00:00
Installing collected packages: groupdocs-conversion-net
Successfully installed groupdocs-conversion-net-24.12
```

### Adding the Package to `requirements.txt`

You can add the dependency to your `requirements.txt` file by including the following line:

```bash
groupdocs-conversion-net==24.12
```

Then, install the package using the following command:

```bash
pip install -r requirements.txt
```

## Download Package from Official Website

To download the GroupDocs.Conversion package for your operating system, please visit the official [GroupDocs Releases website](https://releases.groupdocs.com/conversion/python-net/). Currently, four OS-specific packages are available:

- **Windows 64-bit:** Package name ends with `amd64.whl`
- **Windows 32-bit:** Package name ends with `win32.whl`
- **macOS Apple Silicon:** Package name ends with `arm64.whl`
- **macOS Intel Silicon:** Package name ends with `x86_64.whl`

Choose the appropriate package based on your system's architecture.

### Copy Downloaded File

Copy the downloaded file into your project folder.

### Install Package Using Pip

To install package run the command specific to your your operation system. 

{{< tabs "example2">}}
{{< tab "Windows (64-bit)" >}}
```ps
py -m pip install groupdocs_conversion_net-24.12-py3-none-win_amd64.whl
```
{{< /tab >}}
{{< tab "Windows (32-bit)" >}}
```ps
py -m pip install groupdocs_conversion_net-24.12-py3-none-win32.whl
```
{{< /tab >}}
{{< tab "macOS (Apple Silicon)" >}}
```ps
python3 -m pip install groupdocs_conversion_net-24.12-py3-none-macosx_11_0_arm64.whl
```
{{< /tab >}}
{{< tab "macOS (Intel Silicon)" >}}
```ps
python3 -m pip install groupdocs_conversion_net-24.12-py3-none-macosx_10_14_x86_64.whl
```
{{< /tab >}}
{{< /tabs >}}

Expected output:

```bash
Processing groupdocs_conversion_net-24.12-py3-none-*.whl
Installing collected packages: groupdocs-conversion-net
Successfully installed groupdocs-conversion-net-24.12
```