---
id: licensing-and-subscription
url: conversion/python-net/licensing-and-subscription
title: Licensing
linkTitle: Licensing
weight: 6
description: "Evaluate, apply, and manage licenses for GroupDocs.Conversion for Python via .NET — free trial with limitations, 30-day temporary license, file and stream license loading, and metered licensing."
keywords: license, licensing, free trial, temporary license, metered license, GROUPDOCS_LIC_PATH, set license from file, set license from stream, evaluation limitations, GroupDocs.Conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

To help you quickly explore library and its features, GroupDocs.Conversion provides a Free Trial and a 30-day Temporary License for evaluation, as well as various purchase plans.

Sometimes, to get familiar with the system quickly, you may want to dive into the code right away. To make this easier, GroupDocs.Conversion offers a Free Trial and a 30-day Temporary License for evaluation, along with various purchase plans.

{{< alert style="info" >}}
Please note that general policies and practices guide you on evaluating, licensing, and purchasing our products. See the [Purchase Policies and FAQ](https://purchase.groupdocs.com/policies/) section for details.
{{< /alert >}}

## Free Trial or Temporary License

You can try GroupDocs.Conversion without purchasing a license.

### Free Trial

The evaluation version is identical to the full version — it simply becomes fully licensed when you apply a license. Instructions for setting a license are provided in the following sections.

The evaluation version has the following limitations:
* Only the first three pages are processed.
* Documents with more than three pages are not supported.
* A trial watermark is placed at the top of each page.

### Temporary License

If you'd like to test GroupDocs.Conversion without the limitations of the trial version, you can request a 30-day Temporary License. For more information, see the [Get a Temporary License](https://purchase.groupdocs.com/temporary-license) page.

## How to Set Up a License

{{< alert style="info" >}}
For information on pricing, visit the [Pricing Information](https://purchase.groupdocs.com/pricing/) page.
{{< /alert >}}

Once you’ve obtained a license, follow these instructions to set it up. 

A license should be set:
- Only once per application, and
- Before using any other GroupDocs.Conversion classes.

{{< alert style="tip" >}}
Though the license can be set multiple times per application, it is recommended to set it only once, as repeated calls to the `set_license` method will use unnecessary processing time.
{{< /alert >}}

### Set Environment Variable

You can set the `GROUPDOCS_LIC_PATH` environment variable to the absolute path of the license file. GroupDocs.Conversion will then read this value and apply the license.

{{< tabs "set-license-env-var">}}
{{< tab "Windows (Command Prompt)" >}}
```ps
set GROUPDOCS_LIC_PATH "C:\path\to\your\license\file.lic"
```
{{< /tab >}}
{{< tab "Windows (Powershell)" >}}
```ps
$env:GROUPDOCS_LIC_PATH="C:\path\to\your\license\file.lic"
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
export GROUPDOCS_LIC_PATH="/path/to/your/license/file.lic"
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
export GROUPDOCS_LIC_PATH="/path/to/your/license/file.lic"
```
{{< /tab >}}
{{< /tabs >}}

### Copy License into Project Root Folder

GroupDocs.Conversion can also read a license from the project’s root directory. Consider a simple Python app structure:

```Directory
📂 my-app
 ├──app.py
 ├──source.docx
 ├──groupdocs_conversion_net-26.3-py3-none-*.whl
 └──GroupDocs.Conversion.PythonViaNET.lic
```

When you run the application from the `my-app` folder, GroupDocs.Conversion will check for files with a `.lic` extension in this folder. It will read the `GroupDocs.Conversion.PythonViaNET.lic` file to apply the license.

### Set License from a File

The following code demonstrates setting a license from a file. The example guards the call with an `os.path.exists` check so the script fails loudly when the license file is missing instead of raising an opaque runtime error from the .NET layer.

```python
import os
from groupdocs.conversion import License

def set_license_from_file():
    # Absolute path to the license file
    license_path = os.path.abspath("./GroupDocs.Conversion.PythonViaNET.lic")

    if not os.path.exists(license_path):
        print(f"License file not found: {license_path}")
        print("Place a valid .lic file at that path or set GROUPDOCS_LIC_PATH.")
        return

    # Instantiate License and apply the file
    license = License()
    license.set_license(license_path)
    print(f"License applied from: {license_path}")

if __name__ == "__main__":
    set_license_from_file()
```

### Set License from a Stream

This example shows how to set a license from a stream. Same existence guard — if the `.lic` file isn't there, the script exits cleanly with a human-readable message:

```python
import os
from groupdocs.conversion import License

def set_license_from_stream():
    # Absolute path to the license file
    license_path = os.path.abspath("./GroupDocs.Conversion.PythonViaNET.lic")

    if not os.path.exists(license_path):
        print(f"License file not found: {license_path}")
        print("Place a valid .lic file at that path or set GROUPDOCS_LIC_PATH.")
        return

    # Open the license file as a binary stream and apply it
    with open(license_path, "rb") as license_stream:
        license = License()
        license.set_license(license_stream)
        print(f"License applied from stream: {license_path}")

if __name__ == "__main__":
    set_license_from_stream()
```

### Set Metered License

A [Metered License](https://reference.groupdocs.com/conversion/python-net/groupdocs.conversion/metered) is also available as an alternative to a traditional license file. It is a usage-based licensing model that may be more suitable for customers who prefer to be billed based on actual API feature usage. For more information, refer to the [Metered Licensing FAQ](https://purchase.groupdocs.com/faqs/licensing/metered).

The following sample demonstrates how to use metered licensing. Replace the placeholder `public_key` and `private_key` values with the credentials issued to you — the example guards against the placeholder values and exits with a message if they haven't been edited:

```python
from groupdocs.conversion import Metered

PLACEHOLDER = "******"

def set_metered_license():
    # Set your public and private metered keys
    public_key = PLACEHOLDER
    private_key = PLACEHOLDER

    if public_key == PLACEHOLDER or private_key == PLACEHOLDER:
        print("Metered keys must be set before running this example.")
        print("Edit public_key and private_key with the credentials from")
        print("https://purchase.groupdocs.com/ to enable metered licensing.")
        return

    # Instantiate Metered and apply the keys
    metered = Metered()
    metered.set_metered_key(public_key, private_key)

    # Get number of MBs processed
    mb_processed = metered.get_consumption_quantity()
    print("MB processed:", mb_processed)

    # Get number of credits used
    credits_used = metered.get_consumption_credit()
    print("Credits used:", credits_used)

if __name__ == "__main__":
    set_metered_license()
```
