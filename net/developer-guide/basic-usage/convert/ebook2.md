---
id: convert-ebook2
url: conversion/net/convert/ebook2
title: Convert EBook
weight: 100
description: "Following this article you will learn how to convert ebook documents with couple C# code lines and GroupDocs.Conversion for .NET."
keywords: Convert from Ebook, Convert to Ebook
productName: GroupDocs.Conversion for .NET
toc: True
structuredData:
    showOrganization: True
    application:    
        name: Convert Ebook in C#    
        description: Convert Ebook to PDF natively with high performance using C# language and GroupDocs.Conversion for .NET APIs
        productCode: conversion
        productPlatform: net 
    showVideo: True
    howTo:
        name: How to convert Ebook to PDF in C# 
        description: Learn how to convert Ebook to PDF in C# step by step
        steps:
        - name: Load source Ebook file 
          text: Create an instance of Converter class and pass source Ebook file path as a constructor parameter. You may specify absolute or relative file path as per your requirements. 
        - name: Specify convert options 
          text: Create an instance of PdfConvertOptions class.
        - name: Convert to PDF and save result 
          text: Call Converter class Convert method and pass the filename for the converted PDF file and the PdfConvertOptions object from the previous step as parameters.
---

## About EBook File Format

Ebook files are electronic files that can be opened on digital devices known as eReaders. An eReader can be any device such as a computer, a tablet or a smartphone. The most popular ebook file format is the XML based ePub. An ebook can contain different types of contents such as text, image, and video. Common ebook file extensions and their file formats include EPUB (electronic publication), FB2 (FictionBook 2.0) and Mobi (MobiPocket eBook File).

## Supported EBook File Formats

Following table shows the supported eBook formats as **From** and output document format after conversion as **To.**

| From | To |
| --- | --- |
| [EPUB](https://docs.fileformat.com/ebook/epub/) | eBook ([EPUB](https://docs.fileformat.com/ebook/epub/)),<br/> Image ([TIFF](https://docs.fileformat.com/image/tiff/), [TIF](https://docs.fileformat.com/image/tiff/), [JPG](https://docs.fileformat.com/image/jpg/), [JPEG](https://docs.fileformat.com/image/jpeg/), [PNG](https://docs.fileformat.com/image/png/), [GIF](https://docs.fileformat.com/image/gif/), [BMP](https://docs.fileformat.com/image/bmp/), [ICO](https://docs.fileformat.com/image/ico/), [WMF](https://docs.fileformat.com/image/wmf/), [EMF](https://docs.fileformat.com/image/emf/), [DCM](https://docs.fileformat.com/image/dcm/), [DICOM](https://docs.fileformat.com/image/dicom/), [WEBP](https://docs.fileformat.com/image/webp/), [JP2](https://docs.fileformat.com/image/jp2/), [EMZ](https://docs.fileformat.com/image/emz/), [WMZ](https://docs.fileformat.com/image/wmz/), [SVGZ](https://docs.fileformat.com/image/svgz/), [TGA](https://docs.fileformat.com/image/tga/)),<br/> Page Description Language ([XPS](https://docs.fileformat.com/page-description-language/xps/), [TEX](https://docs.fileformat.com/page-description-language/tex/), [SVG](https://docs.fileformat.com/page-description-language/svg/)),<br/> PDF ([PDF](https://docs.fileformat.com/pdf/)),<br/> Photoshop ([PSD](https://docs.fileformat.com/image/psd/), [PSB](https://docs.fileformat.com/image/psb/)),<br/> Presentation ([PPT](https://docs.fileformat.com/presentation/ppt/), [PPS](https://docs.fileformat.com/presentation/pps/), [PPTX](https://docs.fileformat.com/presentation/pptx/), [PPSX](https://docs.fileformat.com/presentation/ppsx/), [ODP](https://docs.fileformat.com/presentation/odp/), [OTP](https://docs.fileformat.com/presentation/otp/), [POTX](https://docs.fileformat.com/presentation/potx/), [POT](https://docs.fileformat.com/presentation/pot/), [POTM](https://docs.fileformat.com/presentation/potm/), [PPTM](https://docs.fileformat.com/presentation/pptm/), [PPSM](https://docs.fileformat.com/presentation/ppsm/), FODP),<br/> Spreadsheet ([XLS](https://docs.fileformat.com/spreadsheet/xls/), [XLSX](https://docs.fileformat.com/spreadsheet/xlsx/), [XLSM](https://docs.fileformat.com/spreadsheet/xlsm/), [XLSB](https://docs.fileformat.com/spreadsheet/xlsb/), [ODS](https://docs.fileformat.com/spreadsheet/ods/), [XLTX](https://docs.fileformat.com/spreadsheet/xltx/), [XLT](https://docs.fileformat.com/spreadsheet/xlt/), [XLTM](https://docs.fileformat.com/spreadsheet/xltm/), [TSV](https://docs.fileformat.com/spreadsheet/tsv/), [XLAM](https://docs.fileformat.com/spreadsheet/xlam/), [CSV](https://docs.fileformat.com/spreadsheet/csv/), [FODS](https://docs.fileformat.com/spreadsheet/fods/), [DIF](https://docs.fileformat.com/spreadsheet/dif/), [SXC](https://docs.fileformat.com/spreadsheet/sxc/)),<br/> Web ([HTML](https://docs.fileformat.com/web/html/), [HTM](https://docs.fileformat.com/web/htm/), [MHT](https://docs.fileformat.com/web/mht/), [MHTML](https://docs.fileformat.com/web/mhtml/)),<br/> Word Processing ([DOC](https://docs.fileformat.com/word-processing/doc/), [DOCM](https://docs.fileformat.com/word-processing/docm/), [DOCX](https://docs.fileformat.com/word-processing/docx/), [DOT](https://docs.fileformat.com/word-processing/dot/), [DOTM](https://docs.fileformat.com/word-processing/dotm/), [DOTX](https://docs.fileformat.com/word-processing/dotx/), [RTF](https://docs.fileformat.com/word-processing/rtf/), [ODT](https://docs.fileformat.com/word-processing/odt/), [OTT](https://docs.fileformat.com/word-processing/ott/), [TXT](https://docs.fileformat.com/word-processing/txt/), [MD](https://docs.fileformat.com/word-processing/md/)) |
| [MOBI](https://docs.fileformat.com/ebook/mobi/) | eBook ([EPUB](https://docs.fileformat.com/ebook/epub/)),<br/> Image ([TIFF](https://docs.fileformat.com/image/tiff/), [TIF](https://docs.fileformat.com/image/tiff/), [JPG](https://docs.fileformat.com/image/jpg/), [JPEG](https://docs.fileformat.com/image/jpeg/), [PNG](https://docs.fileformat.com/image/png/), [GIF](https://docs.fileformat.com/image/gif/), [BMP](https://docs.fileformat.com/image/bmp/), [ICO](https://docs.fileformat.com/image/ico/), [WMF](https://docs.fileformat.com/image/wmf/), [EMF](https://docs.fileformat.com/image/emf/), [DCM](https://docs.fileformat.com/image/dcm/), [DICOM](https://docs.fileformat.com/image/dicom/), [WEBP](https://docs.fileformat.com/image/webp/), [JP2](https://docs.fileformat.com/image/jp2/), [EMZ](https://docs.fileformat.com/image/emz/), [WMZ](https://docs.fileformat.com/image/wmz/), [SVGZ](https://docs.fileformat.com/image/svgz/), [TGA](https://docs.fileformat.com/image/tga/)),<br/> Page Description Language ([SVG](https://docs.fileformat.com/page-description-language/svg/), [XPS](https://docs.fileformat.com/page-description-language/xps/), [TEX](https://docs.fileformat.com/page-description-language/tex/)),<br/> PDF ([PDF](https://docs.fileformat.com/pdf/)),<br/> Photoshop ([PSD](https://docs.fileformat.com/image/psd/), [PSB](https://docs.fileformat.com/image/psb/)),<br/> Presentation ([PPT](https://docs.fileformat.com/presentation/ppt/), [PPS](https://docs.fileformat.com/presentation/pps/), [PPTX](https://docs.fileformat.com/presentation/pptx/), [PPSX](https://docs.fileformat.com/presentation/ppsx/), [ODP](https://docs.fileformat.com/presentation/odp/), [OTP](https://docs.fileformat.com/presentation/otp/), [POTX](https://docs.fileformat.com/presentation/potx/), [POT](https://docs.fileformat.com/presentation/pot/), [POTM](https://docs.fileformat.com/presentation/potm/), [PPTM](https://docs.fileformat.com/presentation/pptm/), [PPSM](https://docs.fileformat.com/presentation/ppsm/), FODP),<br/> Spreadsheet ([XLS](https://docs.fileformat.com/spreadsheet/xls/), [XLSX](https://docs.fileformat.com/spreadsheet/xlsx/), [XLSM](https://docs.fileformat.com/spreadsheet/xlsm/), [XLSB](https://docs.fileformat.com/spreadsheet/xlsb/), [ODS](https://docs.fileformat.com/spreadsheet/ods/), [XLTX](https://docs.fileformat.com/spreadsheet/xltx/), [XLT](https://docs.fileformat.com/spreadsheet/xlt/), [XLTM](https://docs.fileformat.com/spreadsheet/xltm/), [TSV](https://docs.fileformat.com/spreadsheet/tsv/), [XLAM](https://docs.fileformat.com/spreadsheet/xlam/), [CSV](https://docs.fileformat.com/spreadsheet/csv/), [FODS](https://docs.fileformat.com/spreadsheet/fods/), [DIF](https://docs.fileformat.com/spreadsheet/dif/), [SXC](https://docs.fileformat.com/spreadsheet/sxc/)),<br/> Web ([HTML](https://docs.fileformat.com/web/html/), [HTM](https://docs.fileformat.com/web/htm/), [MHT](https://docs.fileformat.com/web/mht/), [MHTML](https://docs.fileformat.com/web/mhtml/)),<br/> Word Processing ([DOC](https://docs.fileformat.com/word-processing/doc/), [DOCM](https://docs.fileformat.com/word-processing/docm/), [DOCX](https://docs.fileformat.com/word-processing/docx/), [DOT](https://docs.fileformat.com/word-processing/dot/), [DOTM](https://docs.fileformat.com/word-processing/dotm/), [DOTX](https://docs.fileformat.com/word-processing/dotx/), [RTF](https://docs.fileformat.com/word-processing/rtf/), [ODT](https://docs.fileformat.com/word-processing/odt/), [OTT](https://docs.fileformat.com/word-processing/ott/), [TXT](https://docs.fileformat.com/word-processing/txt/), [MD](https://docs.fileformat.com/word-processing/md/)) |

### Convert from EBook

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your Ebook document into another file format.  
For example Ebook to PDF conversion code snippet will look like this:

```csharp
// Load the source Ebook file
using (Converter converter = new Converter("sample.mobi"))
{
    // Set the convert options for PDF format
    PdfConvertOptions options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a Ebook file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to Ebook

On the other hand, converting your files to Ebook format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to Ebook in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (Converter converter = new Converter("sample.pdf"))
{
    // Set the convert options for epub format
    var options = new PdfConvertOptions {
        Format = PdfFileType.Epub
    };
    // Convert to EPUB format
    converter.Convert("converted.epub", options);
}
```
