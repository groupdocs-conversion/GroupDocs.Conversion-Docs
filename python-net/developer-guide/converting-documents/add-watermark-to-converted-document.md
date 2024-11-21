---
id: add-watermark-to-converted-document
url: conversion/python-net/developer-guide/converting-documents/add-watermark-to-converted-document
title: Add a Watermark to Converted Document
weight: 5
description: "Learn how to add a watermark to a document after converting it to another format using GroupDocs.Conversion for Python via .NET."
keywords: Add watermark, Watermark converted document, Document watermarking, GroupDocs.Conversion
productName: GroupDocs.Conversion for Python via .NET
hideChildren: false
toc: true
---

This topic explains how to add a watermark during the conversion process using GroupDocs.Conversion for Python via .NET. The watermark can be applied to a document as it is converted to another format, helping to protect the content and ensure it is identifiable.

To enable watermarking, you can use the `watermark` attribute in the appropriate `ConvertOptions` classes. Below are the supported `ConvertOptions` classes that allow you to configure the watermark during conversion:

{{< alert style="tip" >}}
Looking for advanced watermarking capabilities? While GroupDocs.Conversion offers basic watermarking, you can explore [GroupDocs.Watermark](https://products.groupdocs.com/watermark/) for a comprehensive solution with enhanced features.
{{< /alert >}}

## Supported ConvertOptions Classes

The following `ConvertOptions` classes that provide `watermark` attribute.

- **PdfConvertOptions** – Options for converting to [PDF]({{< ref "conversion/python-net/supported-file-formats#pdf" >}}) format.
- **WordProcessingConvertOptions** – Options for converting to [Word Processing]({{< ref "conversion/python-net/supported-file-formats#word-processing" >}}) formats.
- **SpreadsheetConvertOptions** – Options for converting to [Spreadsheet]({{< ref "conversion/python-net/supported-file-formats#spreadsheet" >}}) formats.
- **PresentationConvertOptions** – Options for converting to [Presentation]({{< ref "conversion/python-net/supported-file-formats#presentation" >}}) formats.
- **ImageConvertOptions** – Options for converting to [Image]({{< ref "conversion/python-net/supported-file-formats#image" >}}) formats (e.g., PNG, JPEG).
- **WebConvertOptions** – Options for converting to [Web]({{< ref "conversion/python-net/supported-file-formats#web" >}}) formats (e.g., HTML).
- **PageDescriptionLanguageConvertOptions** – Options for converting to [Page Description Language]({{< ref "conversion/python-net/supported-file-formats#page-description-language" >}}) formats (e.g., PostScript).
- **EBookConvertOptions** – Options for converting to [EBook]({{< ref "conversion/python-net/supported-file-formats#ebook" >}}) formats (e.g., EPUB, MOBI).
- **DiagramConvertOptions** – Options for converting to [Diagram]({{< ref "conversion/python-net/supported-file-formats#diagram" >}}) formats (e.g., VSDX).

## WatermarkTextOptions Class Attributes

The `WatermarkTextOptions` class is used to configure the appearance of the watermark. The following options can be configured for adding a watermark:

- **text**: The text to be used for the watermark.
- **font**: The font name used for the watermark text.
- **color**: The color of the watermark text.
- **width**: The width of the watermark.
- **height**: The height of the watermark.
- **top**: The top position of the watermark.
- **left**: The left position of the watermark.
- **rotation_angle**: The rotation angle of the watermark.
- **transparency**: The transparency level of the watermark.
- **background**: Specifies whether the watermark is stamped as a background. If set to `True`, the watermark is placed at the bottom. By default, it is `False`, and the watermark is placed on top of the content.

## Example: Add a Watermark to Converted Document

The following example demonstrates how to convert DOCX document to PDF and add a watermark:

{{< tabs "example-1">}}
{{< tab "add_watermark_to_converted_document.py" >}}  
```python
from groupdocs.pydrawing import Color
from groupdocs.conversion import Converter
from groupdocs.conversion.options.convert import PdfConvertOptions, WatermarkTextOptions

def add_watermark_to_converted_document():
    # Instantiate Converter with the input document 
    with Converter("./professional-services.docx") as converter:
        # Set up the watermark options
        watermark = WatermarkTextOptions("DRAFT")
        watermark.color = Color.from_argb(128, 211, 211, 211) # lite gray
        watermark.top = 10
        watermark.left = 10
        watermark.width = 300
        watermark.height = 300
        watermark.background = True

        # Set up the conversion options
        options = PdfConvertOptions()
        options.watermark = watermark
        
        # Perform the conversion
        converter.convert("./professional-services.pdf", options)    

if __name__ == "__main__":
    add_watermark_to_converted_document()
```
{{< /tab >}}
{{< tab "professional-services.docx" >}}  
{{< tab-text >}}
`professional-services.docx` is the sample file used in this example. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/add-watermark-to-converted-document/professional-services.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "professional-services.pdf" >}}  
{{< tab-text >}}
`professional-services.pdf` is the expected output PDF file. Click [here](/conversion/python-net/_sample_files/developer-guide/converting-documents/add-watermark-to-converted-document/professional-services.pdf) to download it.
{{< /tab-text >}}
{{< /tabs >}}
