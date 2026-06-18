
---
id: convert-document-to-multiple-page-files
url: conversion/python-net/developer-guide/converting-documents/convert-document-to-multiple-page-files
title: Convert a Document to Multiple Page Files
linkTitle: Convert to Multiple Files
weight: 3
description: "Render every page of a multi-page document into its own output file — loop page_number with pages_count=1 and Converter.convert() to produce one PNG, PDF, or image per page with GroupDocs.Conversion for Python via .NET."
keywords: convert to multiple files, per-page output, page_number, pages_count, page loop, convert presentation pages, convert PDF pages to PNG, ImageConvertOptions, GroupDocs.Conversion, python
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

To convert a document into per-page files, use the `Converter.convert(file_path, convert_options)` method together with the `page_number` and `pages_count` attributes on the supported `ConvertOptions` classes:

- **`page_number`**: One-based index of the first page to convert.
- **`pages_count`**: Number of consecutive pages to convert starting from `page_number`.

To produce one output file per page, loop from `1` to `converter.get_document_info().pages_count`, updating `page_number` on each iteration and writing to a different output path. Setting `pages_count = 1` ensures each call emits a single page.

## Supported ConvertOptions Classes

The following `ConvertOptions` classes expose the `page_number` and `pages_count` attributes used in this topic:

- **PdfConvertOptions** – Options for converting to [PDF]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#pdf" >}}) format.
- **ImageConvertOptions** – Options for converting to [Image]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#image" >}}) formats (e.g., PNG, JPEG).
- **WordProcessingConvertOptions** – Options for converting to [Word Processing]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#word-processing" >}}) formats.
- **SpreadsheetConvertOptions** – Options for converting to [Spreadsheet]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#spreadsheet" >}}) formats.
- **PresentationConvertOptions** – Options for converting to [Presentation]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#presentation" >}}) formats.
- **WebConvertOptions** – Options for converting to [Web]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#web" >}}) formats (e.g., HTML).
- **EBookConvertOptions** – Options for converting to [EBook]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#ebook" >}}) formats (e.g., EPUB, MOBI).
- **DiagramConvertOptions** – Options for converting to [Diagram]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#diagram" >}}) formats (e.g., VSDX).
- **PageDescriptionLanguageConvertOptions** – Options for converting to [Page Description Language]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#page-description-language" >}}) formats (e.g., PostScript).
- **CadConvertOptions** – Options for converting to [CAD]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#cad" >}}) formats (e.g., DWG).
- **ThreeDConvertOptions** – Options for converting to [3D]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#3d" >}}) formats.
- **FinanceConvertOptions** – Options for converting to [Finance]({{< ref "conversion/python-net/getting-started/supported-document-formats.md#finance" >}}) formats (e.g., XBRL).

## Example 1: Convert All Pages of a Document and Save Output to a Folder

The following example demonstrates how to convert each slide in a PPTX presentation to a PNG image and save the output images to a specified folder.
 
The file name template for the output files is `converted-page-{page number}.{output file extension}`. In this example, the first slide will be saved as `converted-page-1.png`.

{{< tabs "example-1">}}
{{< tab "convert_all_document_pages.py" >}}  
```python
import os
from groupdocs.conversion import Converter
from groupdocs.conversion.filetypes import ImageFileType
from groupdocs.conversion.options.convert import ImageConvertOptions

def convert_all_document_pages():
    output_folder = "./converted-pages"
    os.makedirs(output_folder, exist_ok=True)

    # Instantiate Converter with the input document
    with Converter("./basic-presentation.pptx") as converter:
        # Determine the total number of pages in the source document
        pages_count = converter.get_document_info().pages_count

        # Instantiate convert options once and reuse them inside the loop
        png_convert_options = ImageConvertOptions()
        png_convert_options.format = ImageFileType.PNG
        png_convert_options.pages_count = 1

        # Convert each page to a separate PNG file
        for page_number in range(1, pages_count + 1):
            png_convert_options.page_number = page_number
            output_file = os.path.join(output_folder, f"converted-page-{page_number}.png")
            converter.convert(output_file, png_convert_options)

if __name__ == "__main__":
    convert_all_document_pages()
```
{{< /tab >}}
{{< tab "basic-presentation.pptx" >}}  
{{< tab-text >}}
`basic-presentation.pptx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/basic-presentation.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "convert-all-document-pages-outputs.zip" >}}  
```text
converted-pages/converted-page-1.png (26 KB)
converted-pages/converted-page-10.png (81 KB)
converted-pages/converted-page-11.png (67 KB)
converted-pages/converted-page-12.png (70 KB)
converted-pages/converted-page-13.png (36 KB)
converted-pages/converted-page-2.png (34 KB)
converted-pages/converted-page-3.png (797 KB)
converted-pages/converted-page-4.png (1262 KB)
converted-pages/converted-page-5.png (75 KB)
converted-pages/converted-page-6.png (33 KB)
[TRUNCATED] (13 files total)
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/convert_all_document_pages/convert-all-document-pages-outputs.zip)
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

        # Specify the single page to convert
        png_convert_options.page_number = 3
        png_convert_options.pages_count = 1

        # Save the converted page to a file
        converter.convert("./slide-3.png", png_convert_options)

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
```text
Binary file (PNG, 797 KB)
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/convert_specific_document_page_to_file/slide-3.png)
{{< /tab >}}
{{< /tabs >}}

## Example 3: Convert a Specific Page and Load Output Into a Stream

{{< alert style="tip" >}} Find out how to get the number of document pages in the [Getting Document Information]({{< ref "conversion/python-net/developer-guide/getting-document-info#example-1-get-basic-document-info" >}}) documentation topic. {{< /alert >}}

If you need the converted page as an in-memory buffer (e.g., to forward it to another API without touching the filesystem afterwards), convert the page to a file first and then read it into a `BytesIO` object:

{{< tabs "example-3">}}
{{< tab "convert_specific_document_page_to_stream.py" >}}  
```python
import io
from groupdocs.conversion import Converter
from groupdocs.conversion.filetypes import ImageFileType
from groupdocs.conversion.options.convert import ImageConvertOptions

def convert_specific_document_page_to_stream():
    page_number_to_convert = 5
    output_file = f"./slide-{page_number_to_convert}.png"

    # Instantiate Converter with the input document
    with Converter("./basic-presentation.pptx") as converter:
        # Instantiate convert options
        png_convert_options = ImageConvertOptions()
        # Define the output format as PNG
        png_convert_options.format = ImageFileType.PNG

        # Specify the single page to convert
        png_convert_options.page_number = page_number_to_convert
        png_convert_options.pages_count = 1

        # Convert and save the page to a file on disk
        converter.convert(output_file, png_convert_options)

    # Load the converted page into an in-memory stream for downstream use
    with open(output_file, "rb") as file_handle:
        page_stream = io.BytesIO(file_handle.read())

    # page_stream now holds the PNG bytes and can be passed to any consumer
    print(f"Loaded {page_stream.getbuffer().nbytes} bytes into memory")

if __name__ == "__main__":
    convert_specific_document_page_to_stream()
```
{{< /tab >}}
{{< tab "basic-presentation.pptx" >}}  
{{< tab-text >}}
`basic-presentation.pptx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/basic-presentation.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "slide-5.png" >}}  
```text
Binary file (PNG, 75 KB)
```
[Download full output](/conversion/python-net/_output_files/developer-guide/converting-documents/convert-document-to-multiple-page-files/convert_specific_document_page_to_stream/slide-5.png)
{{< /tab >}}
{{< /tabs >}}
