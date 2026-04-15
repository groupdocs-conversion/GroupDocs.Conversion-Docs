---
id: installation
url: conversion/python-net/getting-started/installation
title: Installation
linkTitle: Installation
weight: 4
description: "Install GroupDocs.Conversion for Python via .NET on Windows, Linux, or macOS — from PyPI or from a pre-downloaded wheel, including Intel and Apple Silicon builds."
keywords: install, installation, pip, pypi, wheel, whl, Windows, Linux, macOS, Apple Silicon, manylinux, musllinux, requirements.txt, GroupDocs.Conversion, python
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

GroupDocs.Conversion for Python via .NET is distributed as a pre-built wheel on [PyPI](https://pypi.org/project/groupdocs-conversion-net/). The PyPI index hosts a separate wheel for each supported platform pair, and `pip` picks the correct one automatically.

Before installing, confirm your environment matches the supported platforms and Python versions listed in the [System Requirements]({{< ref "conversion/python-net/getting-started/system-requirements.md" >}}) topic.

## Install Package from PyPI

Open a terminal and run the install command for your platform:

{{< tabs "install-pypi">}}
{{< tab "Windows" >}}
```ps
py -m pip install groupdocs-conversion-net
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 -m pip install groupdocs-conversion-net
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m pip install groupdocs-conversion-net
```
{{< /tab >}}
{{< /tabs >}}

After running the command you should see output similar to:

```bash
Collecting groupdocs-conversion-net
  Downloading groupdocs_conversion_net-26.3-py3-none-win_amd64.whl.metadata (7.0 kB)
  Downloading groupdocs_conversion_net-26.3-py3-none-win_amd64.whl (220.3 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 220.3/220.3 MB 2.8 MB/s eta 0:00:00
Installing collected packages: groupdocs-conversion-net
Successfully installed groupdocs-conversion-net-26.3
```

The wheel file name will include a platform suffix that matches your operating system — for example `manylinux_2_17_x86_64` on Ubuntu/Debian, `macosx_11_0_arm64` on Apple Silicon, or `win_amd64` on 64-bit Windows.

## Add the Package to `requirements.txt`

For reproducible environments, pin the package version in your `requirements.txt`:

```txt
groupdocs-conversion-net==26.3
```

Then install all dependencies in one step:

```bash
pip install -r requirements.txt
```

## Install from a Pre-Downloaded Wheel

If your build environment cannot reach PyPI, download the appropriate wheel from the [GroupDocs Releases website](https://releases.groupdocs.com/conversion/python-net/) and install it locally. The following wheels are published for each release:

- **Windows 64-bit**: file name ends with `win_amd64.whl`
- **Windows 32-bit**: file name ends with `win32.whl`
- **Linux x64 (glibc)**: `manylinux_2_17_x86_64.manylinux2014_x86_64.whl`
- **Linux musl (Alpine)**: `musllinux_1_2_x86_64.whl`
- **macOS Apple Silicon**: `macosx_11_0_arm64.whl`
- **macOS Intel**: `macosx_10_14_x86_64.whl`

Place the downloaded wheel into your project folder, then install it:

{{< tabs "install-wheel">}}
{{< tab "Windows (64-bit)" >}}
```ps
py -m pip install groupdocs_conversion_net-26.3-py3-none-win_amd64.whl
```
{{< /tab >}}
{{< tab "Windows (32-bit)" >}}
```ps
py -m pip install groupdocs_conversion_net-26.3-py3-none-win32.whl
```
{{< /tab >}}
{{< tab "Linux (glibc)" >}}
```bash
python3 -m pip install groupdocs_conversion_net-26.3-py3-none-manylinux_2_17_x86_64.manylinux2014_x86_64.whl
```
{{< /tab >}}
{{< tab "Linux (musl)" >}}
```bash
python3 -m pip install groupdocs_conversion_net-26.3-py3-none-musllinux_1_2_x86_64.whl
```
{{< /tab >}}
{{< tab "macOS (Apple Silicon)" >}}
```bash
python3 -m pip install groupdocs_conversion_net-26.3-py3-none-macosx_11_0_arm64.whl
```
{{< /tab >}}
{{< tab "macOS (Intel)" >}}
```bash
python3 -m pip install groupdocs_conversion_net-26.3-py3-none-macosx_10_14_x86_64.whl
```
{{< /tab >}}
{{< /tabs >}}

Expected output:

```bash
Processing groupdocs_conversion_net-26.3-py3-none-*.whl
Installing collected packages: groupdocs-conversion-net
Successfully installed groupdocs-conversion-net-26.3
```

## Next Steps

- Follow the [Quick Start Guide]({{< ref "conversion/python-net/getting-started/quick-start-guide" >}}) to run your first conversion.
- Clone the [examples repository](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-Python-via-.NET) and read [Running Examples]({{< ref "conversion/python-net/getting-started/how-to-run-examples.md" >}}) to try every documented scenario locally.
- If you work with AI agents or LLMs, see [Agents and LLMs]({{< ref "conversion/python-net/agents-and-llm-integration" >}}) for MCP and `AGENTS.md` integration details.
