
---
id: convert-document-to-multiple-page-files
url: conversion/python-net/developer-guide/converting-documents/convert-document-to-multiple-page-files
title: Convert a Document to Multiple Page Files
weight: 3
description: "Learn how to convert a single multi-page document into individual page files in various formats using GroupDocs.Conversion for Python via .NET."
keywords: Convert document, Convert single document to pages, Convert document to multiple files
productName: GroupDocs.Conversion for Python via .NET
hideChildren: false
toc: true
---

This documentation topic covers the conversion of a single multi-page document into individual page files. The following diagram illustrates the process of converting a multi-page file into separate pages:

{{< mermaid class="text-center" >}}
flowchart LR
    %% Nodes
    A["Input Document"]
    B["Conversion"]
    C["Converted Page 1"]
    D["Converted Page 2"]
    E["Converted Page N"]

    %% Edge connections between nodes
    A --> B --> C
    B --> D
    B --> E
{{< /mermaid >}}

To convert and save a document by page, use the following methods of the `Converter` class:

- **`convert_by_page(output_path, convert_options)`**: Converts each page of a document to the specified output format and saves them individually to disk.
- **`convert_by_page(file_path, page_number, convert_options)`**: Converts a specific page of a document and saves it to the specified output file path.
- **`convert_by_page(stream, page_number, convert_options)`**: Converts a specific page of a document and saves it to a provided stream.

## Supported ConvertOptions Classes

The following `ConvertOptions` classes can be used with the `convert_by_page` method:

- **PdfConvertOptions** – Options for converting to [PDF]({{< ref "conversion/python-net/supported-file-formats#pdf" >}}) format.
- **ImageConvertOptions** – Options for converting to [Image]({{< ref "conversion/python-net/supported-file-formats#image" >}}) formats (e.g., PNG, JPEG).
- **WordProcessingConvertOptions** – Options for converting to [Word Processing]({{< ref "conversion/python-net/supported-file-formats#word-processing" >}}) formats.
- **SpreadsheetConvertOptions** – Options for converting to [Spreadsheet]({{< ref "conversion/python-net/supported-file-formats#spreadsheet" >}}) formats.
- **PresentationConvertOptions** – Options for converting to [Presentation]({{< ref "conversion/python-net/supported-file-formats#presentation" >}}) formats.
- **WebConvertOptions** – Options for converting to [Web]({{< ref "conversion/python-net/supported-file-formats#web" >}}) formats (e.g., HTML).
- **EBookConvertOptions** – Options for converting to [EBook]({{< ref "conversion/python-net/supported-file-formats#ebook" >}}) formats (e.g., EPUB, MOBI).
- **DiagramConvertOptions** – Options for converting to [Diagram]({{< ref "conversion/python-net/supported-file-formats#diagram" >}}) formats (e.g., VSDX).
- **PageDescriptionLanguageConvertOptions** – Options for converting to [Page Description Language]({{< ref "conversion/python-net/supported-file-formats#page-description-language" >}}) formats (e.g., PostScript).
- **CadConvertOptions** – Options for converting to [CAD]({{< ref "conversion/python-net/supported-file-formats#cad" >}}) formats (e.g., DWG).
- **ThreeDConvertOptions** – Options for converting to [3D]({{< ref "conversion/python-net/supported-file-formats#3d" >}}) formats.
- **FinanceConvertOptions** – Options for converting to [Finance]({{< ref "conversion/python-net/supported-file-formats#finance" >}}) formats (e.g., XBRL).

## Example 1: Convert All Pages of a Document and Save Output to a Folder

The following example demonstrates how to convert each slide in a PPTX presentation to a PNG image and save the output images to a specified folder.
 
The file name template for the output files is `converted-page-{page number}.{output file extension}`. In this example, the first slide will be saved as `converted-page-1.png`.

{{< tabs "example-1">}}
{{< tab "convert_all_document_pages.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.filetypes import ImageFileType
from groupdocs.conversion.options.convert import ImageConvertOptions

def convert_all_document_pages():
    # Instantiate Converter with the input document 
    with Converter("./basic-presentation.pptx") as converter:
        # Instantiate convert options 
        png_convert_options = ImageConvertOptions()
        # Define the output format as PNG
        png_convert_options.format = ImageFileType.PNG
        
        # Convert all pages and save to the output folder
        converter.convert_by_page("./converted-pages", png_convert_options)    

if __name__ == "__main__":
    convert_all_document_pages()
```
{{< /tab >}}
{{< tab "basic-presentation.pptx" >}}  
{{< tab-text >}}
`basic-presentation.pptx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/basic-presentation.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted-pages" >}}  
{{< tab-text >}}
`converted-pages` is the output folder path for the converted pages. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/converted-pages.zip) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Example 2: Convert a Specific Page and Save Output to a File

{{< alert style="tip" >}} Find out how to get the number of document pages in the [Getting Document Information]({{< ref "conversion/python-net/developer-guide/getting-document-info#example-1-get-basic-document-info" >}}) documentation topic. {{< /alert >}}

The following example shows how to convert a specific slide in a PPTX presentation and save it as a separate file.

{{< tabs "example-2">}}
{{< tab "convert_specific_document_page_to_file.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.filetypes import ImageFileType
from groupdocs.conversion.options.convert import ImageConvertOptions

def convert_specific_document_page_to_file():
    # Instantiate Converter with the input document 
    with Converter("./basic-presentation.pptx") as converter:
        # Instantiate convert options 
        png_convert_options = ImageConvertOptions()
        # Define the output format as PNG
        png_convert_options.format = ImageFileType.PNG
        
        # Set the page number to convert and save it to a file
        page_number_to_convert = 3
        converter.convert_by_page("./slide-3.png", page_number_to_convert, png_convert_options)    

if __name__ == "__main__":
    convert_specific_document_page_to_file()
```
{{< /tab >}}
{{< tab "basic-presentation.pptx" >}}  
{{< tab-text >}}
`basic-presentation.pptx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/basic-presentation.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "slide-3.png" >}}  
{{< tab-text >}}
`slide-3.png` is the expected output PNG image. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/slide-3.png) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Example 3: Convert a Specific Page and Save Output to a Stream

{{< alert style="tip" >}} Find out how to get the number of document pages in the [Getting Document Information]({{< ref "conversion/python-net/developer-guide/getting-document-info#example-1-get-basic-document-info" >}}) documentation topic. {{< /alert >}}

As an alternative, you can specify the stream to save the converted PNG image:

{{< tabs "example-3">}}
{{< tab "convert_specific_document_page_to_stream.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.filetypes import ImageFileType
from groupdocs.conversion.options.convert import ImageConvertOptions

def convert_specific_document_page_to_file():
    # Instantiate Converter with the input document 
    with Converter("./basic-presentation.pptx") as converter:
        # Instantiate convert options 
        png_convert_options = ImageConvertOptions()
        # Define the output format as PNG
        png_convert_options.format = ImageFileType.PNG
        
        # Set the page number to convert and save it to a file
        page_number_to_convert = 5
        with open(f"./slide-{page_number_to_convert}.png", "w+b") as page_stream:
            converter.convert_by_page(page_stream, page_number_to_convert, png_convert_options)    

if __name__ == "__main__":
    convert_specific_document_page_to_file()
```
{{< /tab >}}
{{< tab "basic-presentation.pptx" >}}  
{{< tab-text >}}
`basic-presentation.pptx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/basic-presentation.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "slide-5.png" >}}  
{{< tab-text >}}
`slide-5.png` is the expected output PNG image. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/slide-5.png) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}
