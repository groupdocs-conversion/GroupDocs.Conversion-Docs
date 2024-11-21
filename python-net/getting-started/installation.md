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

The recommended way to manage Python application dependencies is by using a virtual environment. Learn more about virtual environment at [Create and Use Virtual Environments](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments) documentation topic. To create a virtual environment, run the following:

{{< tabs "example1">}}
{{< tab "Windows" >}}
```ps
py -m venv .venv
```
{{< /tab >}}
{{< tab "macOS" >}}
```ps
python3 -m venv .venv
```
{{< /tab >}}
{{< /tabs >}}

Activate a virtual environment:

{{< tabs "example2">}}
{{< tab "Windows" >}}
```ps
.venv\Scripts\activate
```
{{< /tab >}}
{{< tab "macOS" >}}
```ps
source .venv/bin/activate
```
{{< /tab >}}
{{< /tabs >}}


Finally, to install the package, run:

{{< tabs "example3">}}
{{< tab "Windows (64-bit)" >}}
```ps
py -m pip install groupdocs_conversion_net-24.11-py3-none-win_amd64.whl
```
{{< /tab >}}
{{< tab "Windows (32-bit)" >}}
```ps
py -m pip install groupdocs_conversion_net-24.11-py3-none-win32.whl
```
{{< /tab >}}
{{< tab "macOS (Apple Silicon)" >}}
```ps
python3 -m pip install groupdocs_conversion_net-24.11-py3-none-macosx_11_0_arm64.whl
```
{{< /tab >}}
{{< tab "macOS (Intel Silicon)" >}}
```ps
python3 -m pip install groupdocs_conversion_net-24.11-py3-none-macosx_10_14_x86_64.whl
```
{{< /tab >}}
{{< /tabs >}}

Expected output:

```bash
Processing groupdocs_conversion_net-24.11-py3-none-*.whl
Installing collected packages: groupdocs-conversion-net
Successfully installed groupdocs-conversion-net-24.11
```