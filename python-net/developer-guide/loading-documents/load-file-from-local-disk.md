---
id: load-file-from-local-disk
url: conversion/python-net/developer-guide/loading-documents/load-file-from-local-disk
title: Load File From Local Disk
weight: 2
description: "This article demonstrates how to convert a file stored on a local disk using GroupDocs.Conversion for Python via .NET API."
keywords: Convert file from local disk, Convert file
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
---

To load a source file from your local disk, you can use the `Converter` class constructor in GroupDocs.Conversion. The API offers several overloads, allowing flexibility for various settings and options:

* `Converter(file_path)`
* `Converter(file_path, load_options)`
* `Converter(file_path, converter_settings)`
* `Converter(file_path, load_options, converter_settings)`

Each constructor requires the `filePath` parameter, which defines the path to the source file. You can specify this as an absolute or relative path. Note that if the specified file path does not exist, an exception will be raised.

{{< alert style="tip" >}}
GroupDocs.Conversion will access the file only when an action (e.g., conversion) is performed using the `Converter` class instance.
{{< /alert >}}

The following Python example demonstrates loading a file from a local disk and converting it to PDF:

{{< tabs "code-example">}}
{{< tab "convert_docx_to_pdf.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_docx_to_pdf():
    # Specify source file location
    converter = Converter("./business-plan.docx")
    
    # Specify output file location and convert options
    output_path = "./business-plan.pdf"
    pdf_options = PdfConvertOptions()
    
    # Convert and save to output path
    converter.convert(output_path, pdf_options)

if __name__ == "__main__":
    convert_docx_to_pdf()
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-file-from-local-disk/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is converted PDF document. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-file-from-local-disk/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

{{< alert style="warning" >}}
GroupDocs.Conversion determines the file type by its extension. If the file extension is not set, GroupDocs.Conversion will attempt to detect the file type automatically. Depending on the file type and size, automatic file type detection consumes additional resources, such as memory and CPU time. Therefore, we recommend ensuring that a file has the correct extension or using the Converter class constructor that accepts load options.
{{< /alert >}}

### Explanation

- **Load Source File**: The `Converter` class is instantiated with the path to the source document ("business-plan.docx").
- **Conversion Options**: An instance of `PdfConvertOptions` is created to define the settings for PDF conversion.
- **Execute Conversion**: The `convert` method is used to convert the document and save it to the specified output path ("business-plan.pdf").

Refer to the [GroupDocs.Conversion API Reference](https://reference.groupdocs.com/conversion/python-net/) for more details on using load options and other constructor overloads.
