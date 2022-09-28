---
id: convert-to-pdf-with-advanced-options
url: conversion/net/convert-to-pdf-with-advanced-options
title: Convert to PDF with advanced options
weight: 5
description: "Follow this guide and learn how a file convert to pdf with height, width, DPI, margins and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert PDF, Convert to PDF/A, file convert to pdf
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions) to give you control over conversion result when convert to PDF. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions) has the following additional options:

*   [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) - desired result document type. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*
*   [Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/width) - desired image width after conversion
*   [Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/height) - desired image height after conversion
*   [Dpi](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/dpi) - desired page DPI after conversion
*   [Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/password) - if set the converted document will be protected with specified password
*   [MarginTop](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/margintop) - desired page top margin after conversion
*   [MarginBottom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/marginbottom) - desired page bottom margin after conversion
*   [MarginLeft](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/marginleft) - desired page left margin after conversion
*   [MarginRight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/marginright) - desired page right margin after conversion
*   [PdfOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions) - PDF specific convert options
*   [Rotate](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/rotate) - page rotation. Available options are: *None, On90, On180, On270*

Following code snippet shows how to convert to PDF with advanced options.

```csharp
using (Converter converter = new Converter("sample.docx"))
{
    PdfConvertOptions options = new PdfConvertOptions
    {
        PageNumber = 2,
        PagesCount = 1,
        Rotate = Rotation.On180,
        Dpi = 300,
        Width = 1024,
        Height = 768
    };
    converter.Convert("converted.pdf", options);
}
```

### PdfOptions

[PdfOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions) class provides specific options when converting document to different versions of PDF format.

*   [PdfFormat](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/pdfformat) - sets pdf format of the converted document. Available options are: *Default, PdfA\_1A, PdfA\_1B, PdfA\_2A, PdfA\_3A, PdfA2B, PdfA\_2U, PdfA\_3B, PdfA\_3U, v1\_3, v1\_4, v1\_5, v1\_6, v1\_7, PdfX\_1A, PdfX\_3*
*   [RemovePdfACompliance](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/removepdfacompliance) - removes Pdf-A compliance
*   [Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/zoom) - specifies the zoom level in percentage
*   [Linearize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/linearize) - linearizes PDF document for web
*   [Grayscale](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/grayscale) - convert to grayscale PDF
*   [OptimizationOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/optimizationoptions) - PDF optimization options
*   [FormattingOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/formattingoptions) - PDF formatting options

### PdfOptimizationOptions

[PdfOptimizationOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions) class allows to specify options for adjusting PDF conversion process and improve its speed.

*   [LinkDuplicateStreams](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/linkduplicatestreams) - link duplicate streams
*   [RemoveUnusedObjects](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/removeunusedobjects) - remove unused objects
*   [CompressImages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/compressimages) - if set to *true*, all images in the document are re-compressed. The amount of compression and image quality are defined by the [ImageQuality](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/imagequality)
*   [ImageQuality](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/imagequality) - value in percent where 100% is unchanged quality and image size. To decrease the image size set this property to less than 100
*   [UnembedFonts](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/unembedfonts) - make fonts not embedded

### PdfFormattingOptions

[PdfFormattingOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions) class provides different options to change PDF document look.

*   [CenterWindow](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/centerwindow) - specifies whether position of the document's window will be centered on the screen
*   [Direction](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/direction) - sets reading order of text: L2R (left to right) or R2L (right to left). Available options are: *L2R, R2L*
*   [DisplayDocTitle](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/displaydoctitle) - specifies whether document's window title bar should display document title
*   [FitWindow](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/fitwindow) - specifies whether document window must be resized to fit the first displayed page
*   [HideMenuBar](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/hidemenubar) - specifies whether menu bar should be hidden when document is active
*   [HideToolBar](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/hidetoolbar) - specifies whether toolbar should be hidden when document is active
*   [HideWindowUI](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/hidewindowui) - specifies whether user interface elements should be hidden when document is active
*   [NonFullScreenPageMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/nonfullscreenpagemode) - specifying how to display the document on exiting full-screen mode. Available options are: *UseNone, UseOutlines, UseThumbs, FullScreen, UseOC, UseAttachments*
*   [PageLayout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/pagelayout) - sets page layout which shall be used when the document is opened. Available options are: *Default, SinglePage, OneColumn, TwoColumnLeft, TwoColumnRight, TwoPagesLeft, TwoPagesRight*
*   [PageMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/pagemode) - specifying how document should be displayed when opened. Available options are: *UseNone, UseOutlines, UseThumbs, FullScreen, UseOC, UseAttachments*
