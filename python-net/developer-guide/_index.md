---
id: developer-guide
url: conversion/python-net/developer-guide
title: Developer Guide
weight: 4
description: "This section describes how to get started with GroupDocs.Conversion for Python via .NET library in order to convert files"
keywords: convert files, conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: True
toc: True
---

Welcome to the Developer Guide for GroupDocs.Conversion for Python via .NET. This section provides practical code examples designed to help you quickly integrate and use the GroupDocs.Conversion API in your projects.

## Prerequisites

Before proceeding, please review the following topics:

* [System Requirements]({{< ref "conversion/python-net/system-requirements" >}}): Covers the specifications for your system.
* [Installation]({{< ref "conversion/python-net/getting-started/installation" >}}): Provides installation options and instructions.

We recommend to [get a Temporary License](https://purchase.groupdocs.com/temporary-license/) to test all the product features.

## Code Examples

Each code example in this guide is provided as a standalone script that you can copy directly into a `.py` file. You'll find the instructions for running code examples below. 

## Sample Files

Alongside each code example, you will find source and output files that you can download for reference. These output files demonstrate the actual results you can achieve with GroupDocs.Conversion when using a valid license.

- **Source files** are provided as the input files used in each example.
- **Output files** are generated after conversion and are available for download without evaluation watermarks. A valid license was applied during the conversion process by setting the license path through the environment variable `GROUPDOCS_LIC_PATH`.

## How to Run a Code Example

This topic explains how to run a code example from the Developer Guide section. We will demonstrate the process using the [Load File From Local Disk]({{< ref "conversion/python-net/developer-guide/loading-documents/load-file-from-local-disk" >}}) example, but the steps are the same for any example you choose.

### Step 1: Create a folder 

Create a folder by typing `mkdir load-file-from-local-disk` in your terminal and navigate into it with `cd load-file-from-local-disk`.

### Step 2: Create and activate a virtual environment

We recommend using a virtual environment to manage dependencies in Python applications. Learn more about virtual environments in the [Create and Use Virtual Environments](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments) documentation topic.

Create a virtual environment:

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

Activate the virtual environment:

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

### Step 3: Install `groupdocs-conversion-net` package

To install the package, open a terminal and run the following command:

{{< tabs "example3">}}
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

### Step 4: (Optional) Copy or set the license file 

Copy the license file into the folder that you created, or set the environment variable `GROUPDOCS_LIC_PATH` with the absolute path to the license file.

{{< tabs "example5">}}
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
{{< tab "macOS" >}}
```bash
export GROUPDOCS_LIC_PATH="/path/to/your/license/file.lic"
```
{{< /tab >}}
{{< /tabs >}}

### Step 5: Copy a code example to a file 

Create a file named `convert_to_pdf.py` and copy in the code example:

```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_to_pdf():
    # Specify source file location
    converter = Converter("./business-plan.docx")
    
    # Specify output file location and convert options
    output_path = "./business-plan.pdf"
    pdf_options = PdfConvertOptions()
    
    # Convert and save to output path
    converter.convert(output_path, pdf_options)

if __name__ == "__main__":
    convert_to_pdf()
```

### Step 6: Copy the input file

[Download](/conversion/python-net/_sample_files/developer-guide/_index/business-plan.docx) the input file `business-plan.docx` and copy it into the folder.

### Step 7: Run the example code

In your terminal, run the following command:

{{< tabs "example6">}}
{{< tab "Windows" >}}
```ps
py convert_to_pdf.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```ps
python3 convert_to_pdf.py
```
{{< /tab >}}
{{< /tabs >}}

Check for the output file `business-plan.pdf` in the current directory.

## Troubleshooting

If you encounter any issues while running the examples:

- Ensure all dependencies are installed correctly.
- Visit our [Technical Support]({{< ref "conversion/python-net/technical-support" >}}) page for further assistance.

