---
id: convert-files-within-document-containers
url: conversion/python-net/developer-guide/converting-documents/convert-files-within-document-containers
title: Convert Files Within Document Containers
linkTitle: Convert Archives and Containers
weight: 4
description: "Open ZIP, RAR, 7Z, OST, PST, and other container formats, convert their contents, and write a consolidated output document in a single Converter.convert() call with GroupDocs.Conversion for Python via .NET."
keywords: convert archive, convert ZIP, convert RAR, convert 7Z, compressed file, document container, OST, PST, email container, consolidated output, Converter.convert, GroupDocs.Conversion, python
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

The Extraction and Conversion processes are performed within a single call to the `convert(file_path, convert_options)` method of the `Converter` class. GroupDocs.Conversion opens the container, converts the files it holds, and writes a consolidated output document.

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

The following example demonstrates how to convert the contents of a ZIP archive to a single consolidated PDF:

{{< tabs "example-1">}}
{{< tab "convert_files_within_document_container.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_files_within_document_container():
    # Instantiate Converter with the input document container
    with Converter("./compressed.zip") as converter:
        # Instantiate convert options
        pdf_convert_options = PdfConvertOptions()

        # Extract the archive, convert the contained files, and save a consolidated PDF
        converter.convert("./converted.pdf", pdf_convert_options)

if __name__ == "__main__":
    convert_files_within_document_container()
```
{{< /tab >}}
{{< tab "compressed.zip" >}}  
{{< tab-text >}}
`compressed.zip` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-files-within-document-containers/compressed.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.pdf" >}}  
```text
Binary file (PDF, 283 KB)
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/convert-files-within-document-containers/convert_files_within_document_container/converted.pdf)
{{< /tab >}}
{{< /tabs >}}
