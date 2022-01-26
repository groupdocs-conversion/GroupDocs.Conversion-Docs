---
id: convert-to-wordprocessing-with-advanced-options
url: conversion/net/convert-to-wordprocessing-with-advanced-options
title: Convert to WordProcessing with advanced options
weight: 8
description: "Follow this guide and learn how to convert documents to Word and Open Document formats like DOC, DOCX, ODT, OTT formats with height, width, DPI and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert to Word, Convert to WordProcessing, Convert to DOCX, Convert to DOC
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [WordProcessingConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions) to give you control over conversion result when convert to WordProcessing formats. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) from base class [WordProcessingConvertOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions) has the following additional options:

*   **[Format](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert.convertoptions/1/properties/format)** - desired result document type. Available options are: *Doc, Docm, Docx, Dot, Dotx, Rtf, Odt, Ott, Mobi, Txt*
*   **[Width](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions/properties/width)** - desired page width after conversion 
*   **[Height](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions/properties/height)** -  desired page height after conversion  
*   **[Dpi](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions/properties/dpi)** - desired page dpi after conversion  
*   **[Password](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions/properties/password)** - if set, the converted document will be password protected with the specified password
*   **[RtfOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions/properties/rtfoptions)** - RTF specific options. **RtfOptions** class has single option **ExportImagesForOldReaders** - specifies whether the keywords for "old readers" are written to RTF or not. This can significantly affect the size of the RTF document.
*   **[Zoom](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.convert/wordprocessingconvertoptions/properties/zoom)** - specifies the zoom level in percentage

Following code snippet shows how to convert to WordProcessing with advanced options.

```csharp
using (Converter converter = new Converter("sample.pdf"))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        Format = WordProcessingFileType.Odt,
    };
    converter.Convert("converted.odt", options);
}
```
