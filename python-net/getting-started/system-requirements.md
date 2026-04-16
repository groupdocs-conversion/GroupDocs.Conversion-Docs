---
id: system-requirements
url: conversion/python-net/system-requirements
title: System Requirements
linkTitle: System Requirements
weight: 3
description: "System requirements for GroupDocs.Conversion for Python via .NET — supported operating systems, Python versions, and optional platform dependencies."
keywords: GroupDocs.Conversion for Python via .NET, system requirements, Windows, Linux, macOS, Python 3.5
productName: GroupDocs.Conversion for Python via .NET
hideChildren: false
toc: true
---

{{< alert style="info" >}}
GroupDocs.Conversion for Python via .NET does not require any external software such as Microsoft Office or third-party document editors. To install the library, follow the steps in the [Installation]({{< ref "conversion/python-net/getting-started/installation" >}}) guide.
{{< /alert >}}

## Supported Operating Systems

GroupDocs.Conversion for Python via .NET runs on Windows, Linux, and macOS. Choose the wheel that matches your platform — the package ships as a platform-specific `.whl` on PyPI and `pip` will pick the correct one automatically.

### Windows

* Microsoft Windows 10 (x64, x86)
* Microsoft Windows 11 (x64)
* Microsoft Windows Server 2016 and later

### Linux

* Ubuntu 20.04+, Debian 11+, CentOS 8+, Fedora 36+, Alpine 3.16+

### macOS

* macOS 12 (Monterey) and later — Intel and Apple Silicon (M-series)

## Python Version

GroupDocs.Conversion for Python via .NET supports **Python 3.5 through 3.14**. The wheel uses the `py3-none-{platform}` tag, meaning it works with any Python 3.x version in that range without per-version rebuilds.

| Python Version | Supported |
| --- | :---: |
| 3.5  | Yes |
| 3.6  | Yes |
| 3.7  | Yes |
| 3.8  | Yes |
| 3.9  | Yes |
| 3.10 | Yes |
| 3.11 | Yes |
| 3.12 | Yes |
| 3.13 | Yes |
| 3.14 | Yes |

## Package Manager

GroupDocs.Conversion for Python via .NET is distributed via [PyPI](https://pypi.org/project/groupdocs-conversion-net/):

```bash
pip install groupdocs-conversion-net
```

The PyPI index hosts one wheel per platform pair:

| Platform | Wheel suffix |
| --- | --- |
| Windows 64-bit | `py3-none-win_amd64.whl` |
| Windows 32-bit | `py3-none-win32.whl` |
| Linux x64 (glibc) | `py3-none-manylinux_2_17_x86_64.manylinux2014_x86_64.whl` |
| Linux musl (Alpine) | `py3-none-musllinux_1_2_x86_64.whl` |
| macOS Apple Silicon | `py3-none-macosx_11_0_arm64.whl` |
| macOS Intel | `py3-none-macosx_10_14_x86_64.whl` |

## Optional Platform Dependencies

GroupDocs.Conversion uses `libgdiplus` for drawing routines when the source document contains images. On Windows no extra setup is required. On Linux and macOS install `libgdiplus` (and a minimal font set) so that image-bearing documents render correctly.

### Linux

Install the following packages on Debian / Ubuntu derivatives:

```bash
sudo apt-get update
sudo apt-get install -y libgdiplus libfontconfig1 libx11-dev ttf-mscorefonts-installer
```

- **libgdiplus** — Mono library providing a GDI+-compatible API on non-Windows operating systems.
- **libfontconfig1** / **libx11-dev** — needed for drawing functions (image and font rendering).
- **ttf-mscorefonts-installer** — Microsoft-compatible fonts used by many Office-format documents. If `ttf-mscorefonts-installer` is not available, add the `contrib` component to your apt sources:

  ```bash
  sudo sed -i'.bak' 's/$/ contrib/' /etc/apt/sources.list
  sudo apt-get update
  ```

- **ICU** — required by the .NET runtime. On minimal distributions install it explicitly: `sudo apt-get install -y libicu-dev`. Do **not** set `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT`, as it disables culture-sensitive conversions.

### macOS

Install `libgdiplus` using [Homebrew](https://brew.sh/):

```bash
brew install mono-libgdiplus
```

If you see a `DllNotFoundException: libSkiaSharp` error after upgrading, an older system copy of SkiaSharp is shadowing the one bundled with the wheel. Rename it so the bundled copy wins:

```bash
sudo mv /usr/local/lib/libSkiaSharp.dylib /usr/local/lib/libSkiaSharp.dylib.bak
```

### Windows

No extra dependencies — the wheel is self-contained.
