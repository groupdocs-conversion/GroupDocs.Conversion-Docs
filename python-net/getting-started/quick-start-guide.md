---
id: quick-start-guide
url: conversion/python-net/getting-started/quick-start-guide
title: Quick Start Guide
linkTitle: Quick Start Guide
second_title: A simple example of how to use GroupDocs.Conversion for Python via .NET
weight: 5
keywords: quick start, hello world, get started, first conversion, DOCX to PDF, PDF to PNG, ZIP to PDF, pip install, venv, virtual environment, GroupDocs.Conversion, python
description: "Set up a virtual environment, install groupdocs-conversion-net, and run three minimal examples — DOCX → PDF, PDF → per-page PNG, and ZIP → consolidated PDF — in under five minutes."
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: True
---

This guide provides a quick overview of how to set up and start using GroupDocs.Conversion for Python via .NET. This library enables developers to convert between various file formats (e.g., DOCX, PDF, PNG) with minimal configuration.

## Prerequisites

To proceed, make sure you have:

1. **Configured** environment as described in the [System Requirements]({{< ref "conversion/python-net/getting-started/system-requirements.md" >}}) topic.
2. **Optionally** you may [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/) to test all the product features. 

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
{{< tab "Linux" >}}
```bash
python3 -m venv .venv
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
{{< tab "Linux" >}}
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
source .venv/bin/activate
```
{{< /tab >}}
{{< /tabs >}}

### Install `groupdocs-conversion-net` Package

After activating the virtual environment, run the following command in your terminal to install the latest version of the package:

{{< tabs "example3">}}
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

Ensure the package is installed successfully. You should see the message 

```bash
Successfully installed groupdocs-conversion-net-*
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
```text
Binary file (PDF, 283 KB)
```
[Download full output](/conversion/python-net/_output_files/getting-started/quick-start-guide/convert_docx_to_pdf/business-plan.pdf)
{{< /tab >}}
{{< /tabs >}}

Your folder tree should look similar to the following directory structure:

```Directory
📂 demo-app
 ├──convert_docx_to_pdf.py
 ├──business-plan.docx
 └──GroupDocs.Conversion.lic (Optionally)
```

### Run the App

{{< tabs "run-the-app">}}
{{< tab "Windows" >}}
```ps
py convert_docx_to_pdf.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 convert_docx_to_pdf.py
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

    output_folder = "./converted-pages"
    os.makedirs(output_folder, exist_ok=True)

    # Load PDF document
    with Converter("./annual-review.pdf") as converter:
        # Determine the total number of pages in the source document
        pages_count = converter.get_document_info().pages_count

        # Create convert options and reuse them inside the loop
        png_convert_options = ImageConvertOptions()
        png_convert_options.format = ImageFileType.PNG
        png_convert_options.pages_count = 1

        # Convert each page to a separate PNG file
        for page_number in range(1, pages_count + 1):
            png_convert_options.page_number = page_number
            output_file = os.path.join(output_folder, f"converted-page-{page_number}.png")
            converter.convert(output_file, png_convert_options)

if __name__ == "__main__":
    convert_pdf_pages_to_png()
```
{{< /tab >}}
{{< tab "annual-review.pdf" >}}  
{{< tab-text >}}
`annual-review.pdf` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/annual-review.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "convert-pdf-pages-to-png-outputs.zip" >}}  
```text
converted-pages/converted-page-1.png (1148 KB)
converted-pages/converted-page-2.png (89 KB)
converted-pages/converted-page-3.png (83 KB)
```
[Download full output](/conversion/python-net/_output_files/getting-started/quick-start-guide/convert_pdf_pages_to_png/convert-pdf-pages-to-png-outputs.zip)
{{< /tab >}}
{{< /tabs >}}

Your folder tree should look similar to the following directory structure:

```Directory
📂 demo-app
 ├──annual-review.pdf
 ├──convert_pdf_pages_to_png.py
 └──GroupDocs.Conversion.lic (Optionally)
```

### Run the App

{{< tabs "run_the_app_convert_pdf_pages_to_png">}}
{{< tab "Windows" >}}
```ps
py convert_pdf_pages_to_png.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 convert_pdf_pages_to_png.py
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
- `converter.get_document_info().pages_count`: Retrieves the total number of pages in the source document.
- `ImageConvertOptions()` with `format = ImageFileType.PNG`: Specifies the output format as PNG image.
- The loop updates `png_convert_options.page_number` on each iteration (with `pages_count = 1`) and calls `converter.convert(...)` to write one PNG file per page into the `converted-pages` folder.

## Example 3: Convert files in archive

In this example we'll convert the contents of a ZIP archive to PDF. GroupDocs.Conversion opens the archive, converts the files inside, and produces a single consolidated PDF that contains every converted document. You can download the app that we're going to buid [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/convert_files_in_archive.zip).

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

        # Extract the archive, convert its contents, and save a consolidated PDF
        converter.convert("./converted.pdf", pdf_convert_options)

if __name__ == "__main__":
    convert_files_in_archive()
```
{{< /tab >}}
{{< tab "compressed.zip" >}}  
{{< tab-text >}}
`compressed.zip` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/getting-started/quick-start-guide/compressed.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pdf" >}}  
```text
Binary file (PDF, 283 KB)
```
[Download full output](/conversion/python-net/_output_files/getting-started/quick-start-guide/convert_files_in_archive/converted.pdf)
{{< /tab >}}
{{< /tabs >}}

Your folder tree should look similar to the following directory structure:

```Directory
📂 demo-app
 ├──compressed.zip
 ├──convert_files_in_archive.py
 └──GroupDocs.Conversion.lic (Optionally)
```

### Run the App

{{< tabs "run_the_app_convert_files_in_archive">}}
{{< tab "Windows" >}}
```ps
py convert_files_in_archive.py
```
{{< /tab >}}
{{< tab "Linux" >}}
```bash
python3 convert_files_in_archive.py
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
- `PdfConvertOptions()`: Specifies the output format as PDF.
- `converter.convert("./converted.pdf", pdf_convert_options)`: Extracts the archive, converts its contents, and writes a single consolidated PDF to `converted.pdf`.

## Next Steps

After completing the basics, explore additional resources to enhance your usage:
- [Supported File Formats]({{< ref "conversion/python-net/getting-started/supported-document-formats.md" >}}): Review the full list of supported file types.
- [Licensing]({{< ref "conversion/python-net/getting-started/licensing-and-subscription.md" >}}): Check details on licening and evaluation.
- [Technical Support]({{< ref "conversion/python-net/technical-support" >}}): Contact support for assistance if you encounter issues.
