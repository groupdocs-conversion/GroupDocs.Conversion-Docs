---
id: convert-files-within-document-containers
url: conversion/python-net/developer-guide/converting-documents/convert-files-within-document-containers
title: Convert Files Within Document Containers
weight: 4
description: "Learn how to convert files within document containers, such as compressed files, into various formats using GroupDocs.Conversion for Python via .NET."
keywords: Convert document containers, Convert embedded files, Convert multiple files within document, GroupDocs.Conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: false
toc: true
---

This topic covers how to convert files embedded within document containers, such as compressed or packaged files, into individual output files. The following diagram illustrates the process of extracting and converting files within a document container:

{{< mermaid class="text-center" >}}
flowchart LR
    %% Nodes
    A["Document Container"]
    B["Extraction"]
    C["Conversion"]
    D["Converted File 1"]
    E["Converted File 2"]
    F["Converted File N"]

    %% Edge connections between nodes
    A --> B --> C --> D
    C --> E
    C --> F
{{< /mermaid >}}

The Extraction and Conversion processes are performed within a single call to the `convert_multiple(folder_path, convert_options)` method of the `Converter` class.

## Document Container File Types

The following file types are considered document containers:

### Email and Outlook

- **EML** - Email Message File.
- **EMLX** - Apple Mail Email File.
- **MSG** - Microsoft Outlook Message File.
- **OST** - Outlook Offline Data File.
- **PST** - Outlook Personal Information Store File.

### PDF

- **PDF** - PDF files that contain embedded resources.

### Word Processing

- **DOC** - The older Microsoft Word binary format.
- **DOCX** - The modern Word format.
- **DOT and DOTX** - Word template files.
- **RTF** - Rich Text Format.

### Compression

- **7Z** - 7-Zip Compressed File.
- **BZ2** - Bzip2 Compressed File.
- **CAB** - Windows Cabinet File.
- **CPIO** - CPIO Compressed File.
- **GZ** - Gnu Zipped Archive.
- **GZIP** - Gzip Compressed File.
- **LZ** - Lzip Compressed File.
- **LZMA** - LZMA Compressed File.
- **RAR** - RAR Compressed Archive.
- **TAR** - Consolidated Unix File Archive.
- **XZ** - Xz Compressed File.
- **Z** - Unix Compressed File.
- **ZIP** - ZIP Compressed File.

## Example: Convert Files Within Document Container

The following example demonstrates how to convert each compressed file in ZIP archive to PDF:
 
The file name template for the output files is `{file name}_{source file extension}.{output file extension}`. In this example, compressed file `business-plan.docx` is being saved converted and saved with file name `business-plan_docx.pdf`.

{{< tabs "example-1">}}
{{< tab "convert_files_within_document_container.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_files_within_document_container():
    # Instantiate Converter with the input document 
    with Converter("./compressed.zip") as converter:
        # Instantiate convert options 
        pdf_convert_options = PdfConvertOptions()

        # Extract, convert and save output files in PDF format
        converter.convert_multiple("./converted-files", pdf_convert_options)    

if __name__ == "__main__":
    convert_files_within_document_container()
```
{{< /tab >}}
{{< tab "compressed.zip" >}}  
{{< tab-text >}}
`compressed.zip` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-files-within-document-containers/compressed.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted-files" >}}  
{{< tab-text >}}
`converted-files` is the output folder path for the converted files. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-files-within-document-containers/converted-files.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}
