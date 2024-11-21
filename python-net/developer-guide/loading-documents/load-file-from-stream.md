---
id: load-file-from-stream
url: conversion/python-net/developer-guide/loading-documents/load-file-from-stream
title: Load File From Stream
weight: 3
description: "This article demonstrates how to convert a file from a stream using GroupDocs.Conversion for Python via .NET API."
keywords: convert file from stream, convert file
productName: GroupDocs.Conversion for Python via .NET
hideChildren: False
---

To load a source file from a stream, you can use the `Converter` class constructor in GroupDocs.Conversion. The API provides several overloads to accommodate different settings and options:

* `Converter(file_stream)`
* `Converter(file_stream, load_options)`
* `Converter(file_stream, converter_settings)`
* `Converter(file_stream, load_options, converter_settings)`

Each constructor requires the `stream` parameter, which represents the input stream for the source file. This allows you to load documents directly from memory or other input sources. Be mindful that if the stream is not properly initialized or if it reaches the end unexpectedly, an exception will be raised.

{{< alert style="tip" >}}
GroupDocs.Conversion will access the stream only when an action (e.g., conversion) is performed using the `Converter` class instance.
{{< /alert >}}

## Example 1: Load file from stream with load options

The following Python example demonstrates loading a file from a stream and converting it to PDF. In this example we get and specify a default load options for DOCX file conversion:

{{< tabs "code-example-1">}}
{{< tab "load_file_from_stream.py" >}}  
```python
import os
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def get_file_stream(file_path: str):
    file_stream = open(file_path, "rb")
    return file_stream

def get_load_options(file_path: str):
    file_extension = os.path.splitext(file_path)[1]   
    possible_conversions = Converter.get_possible_conversions_by_extension(file_extension)
    load_options = possible_conversions.load_options
    return load_options

def load_file_from_stream():
    # Set file path
    file_path = "./annual-review.docx"

    # Retrieve file stream and load options
    file_stream = get_file_stream(file_path)
    load_options = get_load_options(file_path)

    # Specify source file stream and load options
    converter = Converter(file_stream, load_options)
    
    # Specify output file location and convert options
    output_path = "./annual-review.pdf"
    pdf_options = PdfConvertOptions()
    
    # Convert and save to output path
    converter.convert(output_path, pdf_options)

if __name__ == "__main__":
    load_file_from_stream()

```
{{< /tab >}}
{{< tab "annual-review.docx" >}}  
{{< tab-text >}}
`annual-review.docx` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-file-from-stream/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "annual-review.pdf" >}}  
{{< tab-text >}}
`annual-review.pdf` is converted PDF document. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-file-from-stream/annual-review.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Retrieve File Stream**: The method `get_file_stream` retrieves a file stream from a storage. 
- **Retrieve Load Options**: The method `get_load_options` retrieves a default load options based on file extension. 
- **Load Source File**: The `Converter` class is instantiated with the source documents stream and load options.
- **Conversion Options**: An instance of `PdfConvertOptions` is created to define the settings for PDF conversion.
- **Execute Conversion**: The `convert` method is used to convert the document and save it to the specified output path ("annual-review.pdf").

## Example 2: Load file from stream and detect file type automatically

When loading a document from stream GroupDocs.Conversion can detect the file type automatically in most cases.

{{< alert style="warning" >}}
Depending on the file type and size, automatic file type detection consumes additional resources such as memory and CPU time. Therefore, we recommend specifying the file type whenever you know the source file type. See `Example 1: Load file from stream with load options` that demonstrates how to specify load options.
{{< /alert >}}

The following Python example demonstrates loading a file from a stream and converting it to PDF:

{{< tabs "code-example-2">}}
{{< tab "detect_file_type_automatically.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def get_file_stream(file_path: str):
    file_stream = open(file_path, "rb")
    return file_stream

def detect_file_type_automatically():
    # Retrieve file stream
    file_path = "./annual-review.docx"
    file_stream = get_file_stream(file_path)

    # Specify source file location
    converter = Converter(file_stream)
    
    # Specify output file location and convert options
    output_path = "./annual-review.pdf"
    pdf_options = PdfConvertOptions()
    
    # Convert and save to output path
    converter.convert(output_path, pdf_options)

if __name__ == "__main__":
    detect_file_type_automatically()
```
{{< /tab >}}
{{< tab "annual-review.docx" >}}  
{{< tab-text >}}
`annual-review.docx` is sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-file-from-stream/annual-review.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "annual-review.pdf" >}}  
{{< tab-text >}}
`annual-review.pdf` is converted PDF document. Click [here](/conversion/python-net/_sample_files/developer-guide/loading-documents/load-file-from-stream/annual-review.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Explanation

- **Retrieve File Stream**: The method `get_file_stream` retrieves a file stream from storage. 
- **Load Source File**: The `Converter` class is instantiated with the source documents stream.
- **Conversion Options**: An instance of `PdfConvertOptions` is created to define the settings for PDF conversion.
- **Execute Conversion**: The `convert` method is used to detect file type of the source document stream, convert the document and save it to the specified output path ("annual-review.pdf").

Refer to the [GroupDocs.Conversion API Reference](https://reference.groupdocs.com/conversion/python-net/) for more details on using load options and other constructor overloads.
