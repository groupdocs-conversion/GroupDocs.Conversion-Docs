---
id: running-examples
url: conversion/python-net/getting-started/running-examples
title: Running Examples
weight: 3
description: "Learn how to run code examples in GroupDocs.Conversion for Python via .NET."
keywords: file conversion, python
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
toc: true
---

This page provides instructions on how to set up and run code examples for GroupDocs.Conversion for Python via .NET. The examples are designed to demonstrate basic usage, including conversion between various file formats, working with files in archives, and retrieving document information.

## Prerequisites

Before running the examples, make sure you have:

1. **Configured** environment as described in the [System Requirements]({{< ref "conversion/python-net/system-requirements" >}}) topic.
2. **Downloaded** or cloned [the GitHub repository](https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-Python-via-.NET) containing the examples.

## Project Structure

The example repository is structured similarly to this documentation, making it easy to find the code examples and related input documents.

```md
📂 Examples
├── getting-started
    ├── quick-start-guide
        ├── **convert_docx_to_pdf.py**
        ├── **convert_files_in_archive.py**
        ├── **convert_pdf_pages_to_png.py**
        ├── annual-review.pdf
        ├── business-plan.docx
        ├── compressed.zip
├── developer-guide
    ├── loading-documents
        ├── get-default-load-options
            ├── **get_default_load_options.py**
        ├── load-file-from-local-disk
            ├── **convert_docx_to_pdf.py**
            ├── business-plan.docx
        ├── load-file-from-stream
            ├── **detect_file_type_automatically.py**
            ├── **load_file_from_stream.py**
            ├── annual-review.docx
        ├── load-password-protected-file
            ├── **load_password_protected_file.py**
            ├── password-protected.docx
    ├── get-document-info
        ├── **get_cad_document_info.py**
        ├── **get_document_info.py**
        ├── **get_email_document_info.py**
        ├── **get_image_document_info.py**
        ├── **get_pdf_document_info.py**
        ├── **get_pm_document_info.py**
        ├── **get_pres_document_info.py**
        ├── **get_sp_document_info.py**
        ├── **get_wp_document_info.py**
        ├── blocks-and-tables.dwg
        ├── business-plan.doc
        ├── cost-analysis.xlsx
        ├── infographic-elements.tiff
        ├── invitation.eml
        ├── lorem-ipsum.txt
        ├── presentation-template.pptx
        ├── sample-with-toc.pdf
        ├── weekly-plan.mpp
    ├── converting-documents
        ├── add-watermark-to-converted-document
            ├── **add_watermark_to_converted_document.py**
            ├── professional-services.docx
        ├── convert-document-to-another-format
            ├── **convert_consecutive_document_pages.py**
            ├── **convert_document_to_another_format.py**
            ├── **convert_specific_document_pages.py**
            ├── business-plan.docx
        ├── convert-document-to-multiple-page-files
            ├── **convert_all_document_pages.py**
            ├── **convert_specific_document_page_to_file.py**
            ├── **convert_specific_document_page_to_stream.py**
            ├── basic-presentation.pptx
            ├── converted-pages
        ├── convert-files-within-document-containers
            ├── **convert_files_within_document_container.py**
            ├── compressed.zip
            ├── converted-files
        ├── get-possible-conversions
            ├── **get_all_possible_conversions.py**
            ├── **get_all_possible_conversions_by_file_extension.py**
            ├── **get_all_possible_conversions_for_current_file.py**
            ├── cost-analysis.xlsx
    ├── logging-and-diagnostics
        ├── **write_logs_to_console.py**
        ├── **write_logs_to_file.py**
        ├── business-plan.docx
├── licensing
    ├── **set_license_from_file.py**
    ├── **set_license_from_stream.py**
    ├── **set_metered_license.py**
├── **run_all_examples.py**
├── requirements.txt
```

## Setup Instructions

1. **Create and Activate Virtual Environment**:  Navigate to the project root directory with `cd ./Examples`. Then create and activate virtual environment:
   
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

### Install the Dependencies

After activating the virtual environment, run the following command in your terminal to install the dependencies:

{{< tabs "example3">}}
{{< tab "Windows" >}}
```ps
py -m pip install -r requirements.txt
```
{{< /tab >}}
{{< tab "macOS" >}}
```bash
python3 -m pip install -r requirements.txt
```
{{< /tab >}}
{{< /tabs >}}

3. **Configure License (Optional)**: If you have a license file, you can set the license path in the `run_all_examples.py` file. By default, GroupDocs.Conversion for Python via .NET looks for the `GROUPDOCS_LIC_PATH` environment variable or for files with the `.lic` extension in the project’s root directory.

   {{< alert style="info" >}}
   Learn more about licensing, evaluation, and how to obtain a temporary license in the [Licensing]({{< ref "conversion/python-net/licensing" >}}) documentation topic.
   {{< /alert >}}

## Running Examples

To run the examples:

1. **Run All Examples**: Execute `run_all_examples.py` to run all examples in the repository.

   {{< tabs "example4">}}
   {{< tab "Windows" >}}
   ```ps
   py run_all_examples.py
   ```
   {{< /tab >}}
   {{< tab "macOS" >}}
   ```bash
   python3 run_all_examples.py
   ```
   {{< /tab >}}
   {{< /tabs >}}

   This script will sequentially run all examples listed in `run_all_examples.py` file, showcasing conversions to different formats, handling files in archives, retrieving document info, and listing possible conversions.

2. **Run a Specific Example**: Navigate to the directory where example script is located and run it.

3. **Output Files**: Most of the examples generates an output file or files, saved in the same folder where the example script is located. Also, you can find all the output files on the corresponding documentation page.

## Troubleshooting

If you encounter any issues while running the examples:

- Ensure that package is installed correctly.
- Visit our [Technical Support]({{< ref "conversion/python-net/technical-support" >}}) page for further assistance.