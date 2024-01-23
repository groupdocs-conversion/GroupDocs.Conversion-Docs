---
id: convert-to-pdf-with-advanced-options
url: conversion/nodejs-java/convert-to-pdf-with-advanced-options
title: Convert to PDF with advanced options
weight: 3
description: "Follow this guide and learn how to convert documents to PDF with height, width, DPI, margins and other customizations using GroupDocs.Conversion for Node.js via Java."
keywords: Convert PDF, Convert to PDF/A
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
[GroupDocs.Conversion](#) provides [PdfConvertOptions](h#) to give you control over conversion result when convert to PDF. Along with [common convert options](#)  [PdfConvertOptions](#) has the following additional options:
          
*   [setFormat](#) specifies desired result document type. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*.
*   [setWidth](#) specifies desired image width after conversion.
*   [setHeight](#) specifies desired image height after conversion.
*   [setDpi](#) specifies desired page DPI after conversion.
*   [setPassword](#) whether set the converted document will be protected with specified password.
*   [setMarginTop](#) specifies desired page top margin after conversion.
*   [setMarginBottom](#) specifies desired page bottom margin after conversion.
*   [setMarginLeft](#) specifies desired page left margin after conversion.
*   [setMarginRight](#) specifies desired page right margin after conversion.
*   [setPdfOptions](#) specifies PDF specific convert options.
*   [setRotate](#) specifies page rotation. Available options are: *None, On90, On180, On270*.


The following code snippet shows how to convert to PDF with advanced options

```js
const loadOptions = new groupdocs.conversion.WordProcessingLoadOptions()
loadOptions.setPassword("12345");

const converter = new groupdocs.conversion.Converter('sample.docx')
const convertOptions = new groupdocs.conversion.PdfConvertOptions();

convertOptions.setPageNumber(2);
convertOptions.setPagesCount(1);
convertOptions.setRotate(groupdocs.conversion.Rotation.On180);
convertOptions.setDpi(300);
convertOptions.setWidth(1024);
convertOptions.setHeight(768);

converter.convert("converted.pdf", convertOptions);
```

### PdfOptions

[PdfOptions](#) class provides specific options when converting document to different versions of PDF format.

*   [setPdfFormat](#) sets pdf format of the converted document. Available options are: *Default, PdfA\_1A, PdfA\_1B, PdfA\_2A, PdfA\_3A, PdfA2B, PdfA\_2U, PdfA\_3B, PdfA\_3U, v1\_3, v1\_4, v1\_5, v1\_6, v1\_7, PdfX\_1A, PdfX\_3*.
*   [setRemovePdfACompliance](#) removes Pdf-A compliance.
*   [setZoom](#) specifies the zoom level in percentage.
*   [setLinearize](#) linearizes PDF document for web.
*   [setGrayscale](#) converts PDF file to grayscale.
*   [setOptimizationOptions](#) specifies PDF optimization options.
*   [setFormattingOptions](#) specifies PDF formatting options.

### PdfOptimizationOptions

[PdfOptimizationOptions](#) class allows to specify options for adjusting PDF conversion process and improve its speed.

*   [setLinkDuplicateStreams](#) removes link duplicate streams.
*   [setRemoveUnusedObjects](#) removes unused objects.
*   [setCompressImages](#) whether set to *true*, all images in the document are re-compressed. The amount of compression and image quality are defined by the [setImageQuality](#).
*   [setImageQuality](#) specifies value in percent where 100% is unchanged quality and image size. To decrease the image size set this property to less than 100.
*   [setUnembedFonts](#) specifies make fonts not embedded.

### PdfFormattingOptions

[PdfFormattingOptions](#) class provides different options to change PDF document look.

*   [setCenterWindow](#) specifies whether position of the document's window will be centered on the screen.
*   [setDirection](#) sets reading order of text: L2R (left to right) or R2L (right to left). Available options are: *L2R, R2L*.
*   [setDisplayDocTitle](#) specifies whether document's window title bar should display document title.
*   [setFitWindow](#) specifies whether document window must be resized to fit the first displayed page.
*   [setHideMenuBar](#) specifies whether menu bar should be hidden when document is active.
*   [setHideToolBar](#) specifies whether toolbar should be hidden when document is active.
*   [setHideWindowUI](#) specifies whether user interface elements should be hidden when document is active.
*   [setNonFullScreenPageMode](#) specifies how to display the document on exiting full-screen mode. Available options are: *UseNone, UseOutlines, UseThumbs, FullScreen, UseOC, UseAttachments*.
*   [setPageLayout](#) sets page layout which shall be used when the document is opened. Available options are: *Default, SinglePage, OneColumn, TwoColumnLeft, TwoColumnRight, TwoPagesLeft, TwoPagesRight*.
*   [setPageMode](#) - specifying how document should be displayed when opened.
