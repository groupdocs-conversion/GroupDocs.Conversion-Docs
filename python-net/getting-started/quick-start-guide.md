---
id: quick-start-guide
url: conversion/python-net/getting-started/quick-start-guide
title: Quick Start Guide  
linkTitle: Quick Start Guide    
second_title: A simple example of how to use GroupDocs.Viewer for Python via .NET
weight: 2
keywords: "hello world, example, get started"
description: "Render files, list and save attachments in any supported format using GroupDocs.Viewer for Python via .NET to experience its simplicity and power in Python."
productName: GroupDocs.Viewer for Python via .NET
hideChildren: False
toc: True
---

This guide provides a quick overview of how to set up and start using GroupDocs.Conversion for Python via .NET. This library enables developers to convert between various file formats (e.g., DOCX, PDF, PNG) with minimal configuration.

## Prerequisites

To proceed, make sure you have:

1. **Configured** environment as described in the [System Requirements]({{< ref "conversion/python-net/system-requirements" >}}) topic.
2. **Downloaded** `whl` file for your operation system from the official [GroupDocs Releases](https://releases.groupdocs.com/conversion/python-net/) website.
3. **Optionally** you may [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/) to test all the product features. 

## Set Up Your Development Environment

For best practices, use a virtual environment to manage dependencies in Python applications. Learn more about virtual environment at [Create and Use Virtual Environments](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments) documentation topic.

### Create and Activate a Virtual Environment

Create a virtual environment:

{{< tabs "example1">}}
{{< tab "Windows" >}}
```ps
py -m venv .venv
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
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
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< /tabs >}}

### Install GroupDocs.Conversion Package

After activating the virtual environment, copy the downloaded OS-specific package into your project directory and install it.

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
```bash
python3 -m pip install groupdocs_conversion_net-24.11-py3-none-macosx_11_0_arm64.whl
```
{{< /tab >}}
{{< tab "macOS (Intel Silicon)" >}}
```bash
python3 -m pip install groupdocs_conversion_net-24.11-py3-none-macosx_10_14_x86_64.whl
```
{{< /tab >}}
{{< /tabs >}}

Ensure the package is installed successfully. You should see the message 

```bash
Successfully installed groupdocs-conversion-net-24.11
```

## Example 1: Convert document

To quickly test the library, let’s convert a DOCX file to PDF. You can also download the app that we're going to buid [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/convert_docx_to_pdf.zip).

{{< tabs "demo_app_convert_docx_to_pdf">}}
{{< tab "convert_docx_to_pdf.py" >}}  
```python
import os
from groupdocs.conversion import License, Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_docx_to_pdf():
    # Get license file absolute path
    license_path = os.path.abspath("./GroupDocs.Conversion.lic")

    if os.path.exists(license_path):
        # Create License and set the path
        license = License()
        license.set_license(license_path)

    # Load DOCX file
    with Converter("./business-plan.docx") as converter:
        # Create convert options
        pdf_convert_options = PdfConvertOptions()

        # Convert DOCX to PDF
        converter.convert("./business-plan.pdf", pdf_convert_options)    

if __name__ == "__main__":
    convert_docx_to_pdf()
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is expected output PDF file. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

Your folder tree should look similar to the following directory structure:

```Directory
📂 demo-app
 ├──convert_docx_to_pdf.py
 ├──business-plan.docx
 ├──groupdocs_conversion_net-24.11-py3-none-*.whl
 └──GroupDocs.Conversion.lic (Optionally)
```

### Run the App

{{< tabs "run-the-app">}}
{{< tab "Windows" >}}
```ps
py convert_docx_to_pdf.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 convert_docx_to_pdf.py
```
{{< /tab >}}
{{< /tabs >}}

After running the app you can deactivate virtual environment by executing `deactivate` or closing your shell.

### Explanation
- `Converter("./business-plan.docx")`: Initializes the converter with the DOCX file.
- `PdfConvertOptions()`: Specifies the output format as PDF.
- `converter.convert("./business-plan.pdf", pdf_convert_options)`: Converts the DOCX file to PDF and saves it as `business-plan.pdf`.

## Example 2: Convert document pages

In this example we'll convert PDF document pages to PNG. You can download the app that we're going to buid [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/convert_pdf_pages_to_png.zip).

{{< tabs "demo_app_convert_pdf_pages_to_png">}}
{{< tab "convert_pdf_pages_to_png.py" >}}  
```python
import os
from groupdocs.conversion import License, Converter
from groupdocs.conversion.filetypes import ImageFileType
from groupdocs.conversion.options.convert import ImageConvertOptions

def convert_pdf_pages_to_png():
    # Get license file absolute path
    license_path = os.path.abspath("./GroupDocs.Conversion.lic")

    if os.path.exists(license_path):
        # Create License and set the path
        license = License()
        license.set_license(license_path)

    # Load PDF document
    with Converter("./annual-review.pdf") as converter:
        # Create convert options
        png_convert_options = ImageConvertOptions()
        png_convert_options.format = ImageFileType.PNG
        
        # Convert document pages and save converted pages in the output folder
        converter.convert_by_page("./converted-pages", png_convert_options)    

if __name__ == "__main__":
    convert_pdf_pages_to_png()
```
{{< /tab >}}
{{< tab "annual-review.pdf" >}}  
{{< tab-text >}}
`annual-review.pdf` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/annual-review.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted-pages" >}}  
{{< tab-text >}}
`converted-pages` is output folder where converted pages are stored. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/converted-pages.zip) to download the output PNG files.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

Your folder tree should look similar to the following directory structure:

```Directory
📂 demo-app
 ├──annual-review.pdf
 ├──convert_pdf_pages_to_png.py
 ├──groupdocs_conversion_net-24.11-py3-none-*.whl
 └──GroupDocs.Conversion.lic (Optionally)
```

### Run the App

{{< tabs "run_the_app_convert_pdf_pages_to_png">}}
{{< tab "Windows" >}}
```ps
py convert_pdf_pages_to_png.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 convert_pdf_pages_to_png.py
```
{{< /tab >}}
{{< /tabs >}}

After running the app you can deactivate virtual environment by executing `deactivate` or closing your shell.

### Explanation
- `Converter("./annual-review.pdf")`: Initializes the converter with the PDF file.
- `ImageConvertOptions()`: Specifies the output format as image.
- `ImageFileType.PNG`: Sets the output image format to PNG.
- `converter.convert_by_page("./converted-pages", png_convert_options)`: Converts the PDF file pages to PNG and saves output file in `converted-pages` folder.

## Example 3: Convert files in archive

In this example we'll convert documents packed into ZIP archive to PDF. You can download the app that we're going to buid [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/convert_files_in_archive.zip).

{{< tabs "demo_app_convert_files_in_archive">}}
{{< tab "convert_files_in_archive.py" >}}  
```python
import os
from groupdocs.conversion import License, Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_files_in_archive():
    # Get license file absolute path
    license_path = os.path.abspath("./GroupDocs.Conversion.lic")

    if os.path.exists(license_path):
        # Create License and set the path
        license = License()
        license.set_license(license_path)

    # Load ZIP file
    with Converter("./compressed.zip") as converter:
        # Create convert options
        pdf_convert_options = PdfConvertOptions()
        
        # Extract ZIP and convert each file to PDF
        converter.convert_multiple("./converted-files", pdf_convert_options)    

if __name__ == "__main__":
    convert_files_in_archive()
```
{{< /tab >}}
{{< tab "compressed.zip" >}}  
{{< tab-text >}}
`compressed.zip` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/compressed.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted-files" >}}  
{{< tab-text >}}
`converted-files` is output folder where files converted to PDF are stored. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/converted-files.zip) to download the output PDF files.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

Your folder tree should look similar to the following directory structure:

```Directory
📂 demo-app
 ├──compressed.zip
 ├──convert_files_in_archive.py
 ├──groupdocs_conversion_net-24.11-py3-none-*.whl
 └──GroupDocs.Conversion.lic (Optionally)
```

### Run the App

{{< tabs "run_the_app_convert_files_in_archive">}}
{{< tab "Windows" >}}
```ps
py convert_files_in_archive.py
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 convert_files_in_archive.py
```
{{< /tab >}}
{{< /tabs >}}

After running the app you can deactivate virtual environment by executing `deactivate` or closing your shell.

### Explanation
- `Converter("./compressed.zip")`: Initializes the converter with the ZIP file.
- `PdfConvertOptions()`: Specifies the output format for files as PDF.
- `converter.convert_multiple("./converted-files", pdf_convert_options)`: Extracts files from ZIP, converts each file to PDF saves output files in `converted-files` folder.

## Next Steps

After completing the basics, explore additional resources to enhance your usage:
- [Supported File Formats]({{< ref "conversion/python-net/supported-file-formats" >}}): Review the full list of supported file types.
- [Licensing]({{< ref "conversion/python-net/licensing" >}}): Check details on licening and evaluation.
- [Technical Support]({{< ref "conversion/python-net/technical-support" >}}): Contact support for assistance if you encounter issues.
