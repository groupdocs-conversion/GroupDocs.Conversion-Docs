---
id: get-document-info
url: conversion/net/get-document-info
title: Get document info
weight: 2
description: "This article explains how to detect document file type and calculate pages count when convert file with GroupDocs.Conversion for .NET."
keywords: 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) allows to get basic document information (like pages count) for every supported document type, which may be useful for converting part of source document or per-page conversion.  
Along with this GroupDocs.Conversion provides additional information for the following document types:

*   CAD drawings - collection of layouts and layers;
*   Email - attachments count, is html body, is encrypted, is signed;
*   PDF document - pages count, is landscaped, is encrypted, author and creation date;
*   Image - width, height, image format;
*   Presentation document - slides count, author, creation date and presentation format;
*   Spreadsheet document - worksheets count, author and creation date;
*   Wordprocessing document - pages count, lines count, words count, author and creation date.

Here is a code snippet to demonstrate how to obtain document info for PDF document.

```csharp
using (Converter converter = new Converter("sample-toc.pdf"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    PdfDocumentInfo pdfInfo = (PdfDocumentInfo) info;
    Console.WriteLine("Author: {0}", pdfInfo.Author);
    Console.WriteLine("Creation date: {0}", pdfInfo.CreationDate);
    Console.WriteLine("Title: {0}", pdfInfo.Title);
    Console.WriteLine("Version: {0}", pdfInfo.Version);
    Console.WriteLine("Pages count: {0}", pdfInfo.PagesCount);
    Console.WriteLine("Width: {0}", pdfInfo.Width);
    Console.WriteLine("Height: {0}", pdfInfo.Height);
    Console.WriteLine("Is landscaped: {0}", pdfInfo.IsLandscape);
    Console.WriteLine("Is Encrypted: {0}", pdfInfo.IsEncrypted);
    foreach (var tocItem in pdfInfo.TableOfContents)
    {
        Console.WriteLine($"{tocItem.Title}: {tocItem.Page}");
    }
}
```

## More resources

### Advanced Usage Topics

To learn more about convert file features, please refer to the [advanced usage section]({{< ref "conversion/net/developer-guide/advanced-usage/_index.md" >}}).

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!