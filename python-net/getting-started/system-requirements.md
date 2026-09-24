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

* Microsoft Windows 10 (x64)
* Microsoft Windows 11 (x64)
* Microsoft Windows Server 2016 and later

### Linux

* Ubuntu 20.04+, Debian 11+, CentOS 8+, Fedora 36+ (glibc-based distributions)

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

The PyPI index hosts one wheel per platform:

| Platform | Wheel suffix |
| --- | --- |
| Windows 64-bit | `py3-none-win_amd64.whl` |
| Linux x64 (glibc) | `py3-none-manylinux1_x86_64.whl` |
| macOS Apple Silicon | `py3-none-macosx_11_0_arm64.whl` |
| macOS Intel | `py3-none-macosx_10_14_x86_64.whl` |

## Optional Platform Dependencies

The wheel bundles its own .NET runtime and native rendering libraries, so there is nothing to install on Windows. On Linux you need fonts and ICU; on macOS, nothing.

{{< alert style="info" >}}
**`libgdiplus` is no longer required.** Releases up to 26.5 rendered through `System.Drawing.Common`, which needs a GDI+ implementation. From **26.9** (conversion engine 26.8 on .NET 10) the cross-platform build uses SkiaSharp and Aspose.Drawing instead, and the Linux and macOS wheels no longer contain `System.Drawing.Common` at all. You can remove `libgdiplus` / `mono-libgdiplus` from your images and provisioning scripts.
{{< /alert >}}

### Linux

Install the following packages on Debian / Ubuntu derivatives:

```bash
sudo apt-get update
sudo apt-get install -y libicu-dev fontconfig ttf-mscorefonts-installer
```

- **ttf-mscorefonts-installer** — Microsoft core fonts (Arial, Times New Roman, …), which the engine looks up by name. **These are required**, not cosmetic: without them, converting an image to PDF fails with `Cannot find any fonts installed on the system`, and metric-compatible substitutes such as `fonts-liberation` alone are not enough. The package lives in Debian's `contrib` component, which is not enabled on slim base images — add it first:

  ```bash
  sudo sed -i'.bak' 's/$/ contrib/' /etc/apt/sources.list
  sudo apt-get update
  ```

  Run `sudo fc-cache -f` afterwards so fontconfig picks the fonts up.

- **fontconfig** — font discovery and caching.
- **ICU** — required by the .NET runtime. On minimal distributions install it explicitly: `sudo apt-get install -y libicu-dev`. Do **not** set `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT`, as it disables culture-sensitive conversions.

### macOS

No extra packages are needed. macOS ships the fonts and rendering libraries the wheel relies on.

If you see a `DllNotFoundException: libSkiaSharp` error after upgrading, an older system copy of SkiaSharp is shadowing the one bundled with the wheel. Rename it so the bundled copy wins:

```bash
sudo mv /usr/local/lib/libSkiaSharp.dylib /usr/local/lib/libSkiaSharp.dylib.bak
```

### Windows

No extra dependencies — the wheel is self-contained.
