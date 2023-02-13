---
id: convert-to-pdf-with-advanced-options
url: conversion/net/convert-to-pdf-with-advanced-options
title: Convert to PDF with advanced options
weight: 5
description: "Follow this guide and learn how a file convert to pdf with height, width, DPI, margins and other customizations using GroupDocs.Conversion for .NET."
keywords: Convert PDF, Convert to PDF/A, file convert to pdf
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides the [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions) class to give you control over conversion results. Along with [common convert options]({{< ref "conversion/net/developer-guide/advanced-usage/converting/common-conversion-options/_index.md" >}}) you can specify the following additional options via the [PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions) class:

*   [Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions-1/format/) - sets the desired file type the input document should be converted to.
*   [Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/width) - sets the desired image width after conversion.
*   [Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/height) - sets the desired image height after conversion.
*   [Dpi](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/dpi) - sets the desired page DPI after conversion
*   [Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/password) - when specified, the resulting document will be protected with the specified password.
*   [MarginTop](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/margintop) - sets the desired page top margin after conversion.
*   [MarginBottom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/marginbottom) - sets the desired page bottom margin after conversion.
*   [MarginLeft](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/marginleft) - sets the desired page left margin after conversion.
*   [MarginRight](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/marginright) - sets the desired page right margin after conversion.
*   [PdfOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions) - defines the PDF-specific convert options. See [below](#pdfoptions).
*   [Rotate](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions/rotate) - sets the page rotation angle. Available options are: *None, On90, On180, On270*.

The following code snippet shows how to convert to PDF with advanced options:

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

The [PdfOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions) class provides specific options when converting documents to different versions of PDF format.

*   [PdfFormat](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/pdfformat) - sets the specific PDF format of the converted document. Available options are: *Default, PdfA\_1A, PdfA\_1B, PdfA\_2A, PdfA\_3A, PdfA2B, PdfA\_2U, PdfA\_3B, PdfA\_3U, v1\_3, v1\_4, v1\_5, v1\_6, v1\_7, PdfX\_1A, PdfX\_3*.
*   [RemovePdfACompliance](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/removepdfacompliance) - whether to remove the Pdf-A compliance.
*   [Zoom](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/zoom) - specifies the zoom level in percentage.
*   [Linearize](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/linearize) - whether to linearize the document for the Web.
*   [Grayscale](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/grayscale) - whether to convert the document to grayscale.
*   [OptimizationOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/optimizationoptions) - defines the PDF optimization options. See [below](#pdfoptimizationoptions).
*   [FormattingOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptions/formattingoptions) - defines the PDF formatting options. See [below](#pdfformattingoptions).

The following code snippet shows how to specify options via the `PdfOptions` class:

```csharp
using (Converter converter = new Converter("sample.docx"))
{

    PdfConvertOptions options = new PdfConvertOptions
    {        
        PdfOptions = new PdfOptions
        {
            Grayscale = true,
            Zoom = 200
        }
    };
    converter.Convert("converted.pdf", options);
}
```

### PdfOptimizationOptions

The [PdfOptimizationOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions) class specifies options for adjusting the PDF conversion process and improving its speed.

*   [LinkDuplicateStreams](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/linkduplicatestreams) - whether to link duplicate streams.
*   [RemoveUnusedObjects](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/removeunusedobjects) - whether to remove unused objects.
*   [RemoveUnusedStreams](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/removeunusedstreams) - whether to remove unused streams.
*   [CompressImages](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/compressimages) - whether to re-compress all the images in the document. The amount of compression is defined by the [ImageQuality](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/imagequality) property.
*   [ImageQuality](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/imagequality) - defines the quality (in percentage) of image compression. Effective when the `CompressImages` property is set to `true`. To keep the original quality and image size set this property to 100. To decrease the image size set this property to less than 100.
*   [UnembedFonts](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfoptimizationoptions/unembedfonts) - whether to replace the embedded fonts with references to these fonts. Decreases the file size, but may change the original design of the document.

The following code snippet shows how to specify PDF optimization options:

```csharp
using (Converter converter = new Converter("sample.docx"))
{

    PdfConvertOptions options = new PdfConvertOptions
    {        
        PdfOptions = new PdfOptions
        {
            OptimizationOptions = new PdfOptimizationOptions
            { 
                CompressImages = true,
                ImageQuality = 70,
                UnembedFonts = true
            }
        }
    };
    converter.Convert("converted.pdf", options);
}
```

### PdfFormattingOptions

The [PdfFormattingOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions) class provides different options to change the formatting of the resulting document.

*   [CenterWindow](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/centerwindow) - whether to position the document's window in the center of the screen.
*   [Direction](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/direction) - defines the reading direction of the document: left to right or right to left. Available options are: *L2R, R2L*
*   [DisplayDocTitle](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/displaydoctitle) - whether to display the document title in the window's title bar.
*   [FitWindow](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/fitwindow) - whether to resize the document window to fit the first displayed page.
*   [HideMenuBar](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/hidemenubar) - whether to hide the menu bar when the document is active.
*   [HideToolBar](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/hidetoolbar) - whether to hide the toolbar when the document is active.
*   [HideWindowUI](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/hidewindowui) - whether to hide user interface elements when the document is active.
*   [NonFullScreenPageMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/nonfullscreenpagemode) - defines how to display the document when switching from the full-screen mode. Available options are: *UseNone, UseOutlines, UseThumbs, FullScreen, UseOC, UseAttachments*
*   [PageLayout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/pagelayout) - defines the page layout to use when the document is opened. Available options are: *Default, SinglePage, OneColumn, TwoColumnLeft, TwoColumnRight, TwoPagesLeft, TwoPagesRight*
*   [PageMode](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfformattingoptions/pagemode) - defines how to display the document when it is opened. Available options are: *UseNone, UseOutlines, UseThumbs, FullScreen, UseOC, UseAttachments*

The following code snippet shows how to specify PDF formatting options:

```csharp
using (Converter converter = new Converter("sample.docx"))
{

    PdfConvertOptions options = new PdfConvertOptions
    {        
        PdfOptions = new PdfOptions
        {
            FormattingOptions = new PdfFormattingOptions
            { 
                FitWindow = true,
                HideWindowUI = true,
                PageMode = PdfPageMode.UseThumbs
            }
        }
    };
    converter.Convert("converted.pdf", options);
}
```