---
id: convert-document-to-another-format
url: conversion/python-net/developer-guide/converting-documents/convert-document-to-another-format
title: Convert a Document to Another Format
weight: 2
description: "Learn how to convert a single document to another format using GroupDocs.Conversion for Python via .NET."
keywords: Convert document, Convert single document
productName: GroupDocs.Conversion for Python via .NET
hideChildren: false
toc: true
---

This documentation topic covers the conversion of a single document to another format, where only one document is produced as output. The following diagram illustrates the process of converting a file from one format to another:

{{< mermaid class="text-center" >}}
flowchart LR
    %% Nodes
    A["Input Document (e.g. DOCX)"]
    B["Conversion"]
    C["Converted Document (e.g. PDF)"]

    %% Edge connections between nodes
    A --> B --> C
{{< /mermaid >}}

To convert and save a document, use the following `Converter` class methods:

- **`convert(file_path, convert_options)`**: Converts a document to a specified single output format and saves it to a file, such as converting a DOCX to PDF.
- **`convert(stream, convert_options)`**: Converts the document and writes it to a provided stream instead of a file path.

## Convert a Complete Document 

The following list of `ConvertOptions` classes can be used to convert a document to a specific single output format:

- **PdfConvertOptions** – Options for converting to [PDF]({{< ref "conversion/python-net/supported-file-formats#pdf" >}}) format.
- **WordProcessingConvertOptions** – Options for converting to [Word Processing]({{< ref "conversion/python-net/supported-file-formats#word-processing" >}}) formats.
- **SpreadsheetConvertOptions** – Options for converting to [Spreadsheet]({{< ref "conversion/python-net/supported-file-formats#spreadsheet" >}}) formats.
- **PresentationConvertOptions** – Options for converting to [Presentation]({{< ref "conversion/python-net/supported-file-formats#presentation" >}}) formats.
- **ImageConvertOptions** – Options for converting to [Image]({{< ref "conversion/python-net/supported-file-formats#image" >}}) formats (e.g., PNG, JPEG).
- **WebConvertOptions** – Options for converting to [Web]({{< ref "conversion/python-net/supported-file-formats#web" >}}) formats (e.g., HTML).
- **PageDescriptionLanguageConvertOptions** – Options for converting to [Page Description Language]({{< ref "conversion/python-net/supported-file-formats#page-description-language" >}}) formats (e.g., PostScript).
- **EBookConvertOptions** – Options for converting to [EBook]({{< ref "conversion/python-net/supported-file-formats#ebook" >}}) formats (e.g., EPUB, MOBI).
- **EmailConvertOptions** – Options for converting to [Email]({{< ref "conversion/python-net/supported-file-formats#email-and-outlook" >}}) formats (e.g., EML, MSG).
- **DiagramConvertOptions** – Options for converting to [Diagram]({{< ref "conversion/python-net/supported-file-formats#diagram" >}}) formats (e.g., VSDX).
- **CadConvertOptions** – Options for converting to [CAD]({{< ref "conversion/python-net/supported-file-formats#cad" >}}) formats (e.g., DWG).
- **ThreeDConvertOptions** – Options for converting to [3D]({{< ref "conversion/python-net/supported-file-formats#3d" >}}) formats.
- **ProjectManagementConvertOptions** – Options for converting to [Project Management]({{< ref "conversion/python-net/supported-file-formats#project-management" >}}) formats (e.g., MPP).
- **GisConvertOptions** – Options for converting to [GIS]({{< ref "conversion/python-net/supported-file-formats#gis" >}}) formats.
- **FontConvertOptions** – Options for converting to [Font]({{< ref "conversion/python-net/supported-file-formats#font" >}}) formats (e.g., TTF, OTF).
- **FinanceConvertOptions** – Options for converting to [Finance]({{< ref "conversion/python-net/supported-file-formats#finance" >}}) formats (e.g., XBRL).
- **CompressionConvertOptions** – Options for converting to [Compression]({{< ref "conversion/python-net/supported-file-formats#compression" >}}) formats (e.g., ZIP).
- **NoConvertOptions** – A special option class that instructs the converter to copy the source document without any modifications.

### Example 1: Convert a Document to Another Format

The following example demonstrates how to convert a DOCX file to PDF:

{{< tabs "example-1">}}
{{< tab "convert_document_to_another_format.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_document_to_another_format():
    # Instantiate Converter with the input document 
    with Converter("./business-plan.docx") as converter:
        # Instantiate convert options to define the output format
        pdf_convert_options = PdfConvertOptions()
        
        # Convert the input document to PDF
        converter.convert("./business-plan.pdf", pdf_convert_options)    

if __name__ == "__main__":
    convert_document_to_another_format()
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.pdf" >}}  
{{< tab-text >}}
`business-plan.pdf` is the expected output PDF file. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/business-plan.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Example 2: Specify Output Format

By default, each of the `ConvertOptions` classes has its own default target format. For example, the default output format for [WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/python-net/groupdocs.conversion.options.convert/wordprocessingconvertoptions/) is [DOCX](https://reference.groupdocs.com/conversion/python-net/groupdocs.conversion.filetypes/wordprocessingfiletype/docx/).

To set a different output format, use the `format` property. The following example demonstrates how to specify the target format as `TXT` when converting a `DOCX` file:

{{< tabs "example-2">}}
{{< tab "specify_output_format.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import WordProcessingConvertOptions
from groupdocs.conversion.filetypes import WordProcessingFileType

def specify_output_format():
    # Instantiate Converter with the input document 
    with Converter("./business-plan.docx") as converter:
        # Instantiate convert options to define the output format
        word_convert_options = WordProcessingConvertOptions()
        # Set the output fomormat to TXT
        word_convert_options.format = WordProcessingFileType.TXT
        
        # Convert the input document to TXT
        converter.convert("./business-plan.txt", word_convert_options)    

if __name__ == "__main__":
    specify_output_format()
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "business-plan.txt" >}}  
{{< tab-text >}}
`business-plan.txt` is the expected output TXT file. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/business-plan.txt) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Specify Document Pages to Convert

{{< alert style="tip" >}} Find out how to get the number of document pages in the [Getting Document Information]({{< ref "conversion/python-net/developer-guide/getting-document-info#example-1-get-basic-document-info" >}}) documentation topic. {{< /alert >}}

To convert specific document pages, you can use the following `ConvertOptions` classes, which provide `pages`, `page_number`, and `pages_count` attributes. These options allow you to specify individual pages or a range of pages to convert.

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

### Example 1: Convert Specific Document Pages to Another Format

You can specify which document pages you would like to convert, as shown in the following example:

{{< tabs "example-3">}}
{{< tab "convert_specific_document_pages.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_specific_document_pages():
    # Instantiate Converter with the input document 
    with Converter("./business-plan.docx") as converter:
        # Instantiate convert options to define the output format
        pdf_convert_options = PdfConvertOptions()
        # Specify which document pages to convert
        pdf_convert_options.pages = [1, 3, 5]

        # Convert the specified pages of the input document to PDF
        converter.convert("./pages-1-3-5.pdf", pdf_convert_options)    

if __name__ == "__main__":
    convert_specific_document_pages()
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "pages-1-3-5.pdf" >}}  
{{< tab-text >}}
`pages-1-3-5.pdf` is the expected output PDF file. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/pages-1-3-5.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Example 2: Convert N Consecutive Pages

As an alternative, you can specify a number of consecutive pages to convert, as shown in the following example:

{{< tabs "example-4">}}
{{< tab "convert_consecutive_document_pages.py" >}}  
```python
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions

def convert_consecutive_document_pages():
    # Instantiate Converter with the input document 
    with Converter("./business-plan.docx") as converter:
        # Instantiate convert options to define the output format
        pdf_convert_options = PdfConvertOptions()
        # Specify the starting page and number of pages to convert
        pdf_convert_options.page_number = 1
        pdf_convert_options.pages_count = 5

        # Convert the specified range of pages in the document to PDF
        converter.convert("./pages-1-through-5.pdf", pdf_convert_options)    

if __name__ == "__main__":
    convert_consecutive_document_pages()
```
{{< /tab >}}
{{< tab "business-plan.docx" >}}  
{{< tab-text >}}
`business-plan.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/business-plan.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "pages-1-through-5.pdf" >}}  
{{< tab-text >}}
pages-1-through-5.pdf` is the expected output PDF file. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/convert-document-to-another-format/pages-1-through-5.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}


