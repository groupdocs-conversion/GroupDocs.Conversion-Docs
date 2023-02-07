---
id: convert-note
url: conversion/net/convert/note
title: Convert note-taking formats
linkTitle: Notes
weight: 80
description: "Following this article you will learn how to convert Note documents to other formats with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from Notes, Convert from OneNote, Convert OneNote
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert OneNote in C#    
        description: Convert OneNote to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert OneNote to PDF in C# 
        description: Learn how to convert OneNote to PDF in C# step by step
        steps:
        - name: Load source OneNote file 
          text: Create an instance of Converter class and pass source OneNote file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About note-taking file formats

Note-taking program files contain sections and pages for storing notes. A note document can be as simple as a text document as well as more detailed consisting of digital images, audio/video clips, and hand sketch drawings.

Common OneNote file extensions and their associated file formats is .ONE.

## Supported note-taking file conversions

| From | To |
| --- | --- |
| ONE | eBook: [AZW3](https://docs.fileformat.com/ebook/azw3/), [EPUB](https://docs.fileformat.com/ebook/epub/)<br/> Image: [BMP](https://docs.fileformat.com/image/bmp/), [DCM](https://docs.fileformat.com/image/dcm/), [DICOM](https://docs.fileformat.com/image/dicom/), [EMF](https://docs.fileformat.com/image/emf/), [EMZ](https://docs.fileformat.com/image/emz/), [GIF](https://docs.fileformat.com/image/gif/), [ICO](https://docs.fileformat.com/image/ico/), [JP2](https://docs.fileformat.com/image/jp2/), [JPEG](https://docs.fileformat.com/image/jpeg/), JPG, [PNG](https://docs.fileformat.com/image/png/), [PSB](https://docs.fileformat.com/image/psb/), [PSD](https://docs.fileformat.com/image/psd/), [SVGZ](https://docs.fileformat.com/image/svgz/), [TGA](https://docs.fileformat.com/image/tga/), TIF, [TIFF](https://docs.fileformat.com/image/tiff/), [WEBP](https://docs.fileformat.com/image/webp/), [WMF](https://docs.fileformat.com/image/wmf/), [WMZ](https://docs.fileformat.com/image/wmz/)<br/> PDF: [PDF](https://docs.fileformat.com/view/pdf/)<br/> Spreadsheet: [CSV](https://docs.fileformat.com/spreadsheet/csv/), [DIF](https://docs.fileformat.com/spreadsheet/dif/), [FODS](https://docs.fileformat.com/spreadsheet/fods/), [ODS](https://docs.fileformat.com/spreadsheet/ods/), [SXC](https://docs.fileformat.com/spreadsheet/sxc/), [TSV](https://docs.fileformat.com/spreadsheet/tsv/), [XLAM](https://docs.fileformat.com/spreadsheet/xlam/), [XLS](https://docs.fileformat.com/spreadsheet/xls/), [XLSB](https://docs.fileformat.com/spreadsheet/xlsb/), [XLSM](https://docs.fileformat.com/spreadsheet/xlsm/), [XLSX](https://docs.fileformat.com/spreadsheet/xlsx/), [XLT](https://docs.fileformat.com/spreadsheet/xlt/), [XLTM](https://docs.fileformat.com/spreadsheet/xltm/), [XLTX](https://docs.fileformat.com/spreadsheet/xltx/)<br/> Page Description Language: [SVG](https://docs.fileformat.com/page-description-language/svg/), [TEX](https://docs.fileformat.com/page-description-language/tex/), [XPS](https://docs.fileformat.com/page-description-language/xps/)<br/> Presentation: FODP, [ODP](https://docs.fileformat.com/presentation/odp/), [OTP](https://docs.fileformat.com/presentation/otp/), [POT](https://docs.fileformat.com/presentation/pot/), [POTM](https://docs.fileformat.com/presentation/potm/), [POTX](https://docs.fileformat.com/presentation/potx/), [PPS](https://docs.fileformat.com/presentation/pps/), [PPSM](https://docs.fileformat.com/presentation/ppsm/), [PPSX](https://docs.fileformat.com/presentation/ppsx/), [PPT](https://docs.fileformat.com/presentation/ppt/), [PPTM](https://docs.fileformat.com/presentation/pptm/), [PPTX](https://docs.fileformat.com/presentation/pptx/)<br/> Web: [HTM](https://docs.fileformat.com/web/htm/), [HTML](https://docs.fileformat.com/web/html/), [MHT](https://docs.fileformat.com/web/mht/), [MHTML](https://docs.fileformat.com/web/mhtml/)<br/> Word Processing: [DOC](https://docs.fileformat.com/word-processing/doc/), [DOCM](https://docs.fileformat.com/word-processing/docm/), [DOCX](https://docs.fileformat.com/word-processing/docx/), [DOT](https://docs.fileformat.com/word-processing/dot/), [DOTM](https://docs.fileformat.com/word-processing/dotm/), [DOTX](https://docs.fileformat.com/word-processing/dotx/), [MD](https://docs.fileformat.com/word-processing/md/), [ODT](https://docs.fileformat.com/word-processing/odt/), [OTT](https://docs.fileformat.com/word-processing/ott/), [RTF](https://docs.fileformat.com/word-processing/rtf/), [TXT](https://docs.fileformat.com/word-processing/txt/)<br/>  |

## Convert from note-taking formats

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your OneNote document into another file format.  
For example OneNote to PDF conversion code snippet will look like this:

```csharp
// Load the source OneNote file
using (Converter converter = new Converter("sample.one"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a OneNote file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}
