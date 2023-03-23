---
id: get-document-info
url: conversion/net/get-document-info
title: Get document info
weight: 2
description: "This article explains how to detect the document's file type and calculate the number of pages when converting a file with GroupDocs.Conversion for .NET."
keywords: detect document, calculate pages, detect document file type
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
To get document information use the [`Converter.GetDocumentInfo()`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/getdocumentinfo/) method. It returns a [`DocumentInfo`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/documentinfo/) object with common information common for every supported document - format, creation date, size, and page count. 

To iterate through the document information properties, you can use the `PropertyNames` and `Item` enumerators. The following code snippet demonstrates how to list all the available document information properties:

```csharp
using (Converter converter = new Converter("sample.txt"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    
    foreach (var propertyName in info.PropertyNames)
    {
        Console.WriteLine(propertyName + ": "+ info[propertyName]);
    }
}
```
Depending on the format type, the resulting `DocumentInfo` object also contains some additional information:

* [`PDF documents`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/pdfdocumentinfo/) - title, table of contents, author, whether it is encrypted and so on;
* [`Wordprocessing documents`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/wordprocessingdocumentinfo/) - title, table of contents, author, lines count, words count, whether it is password protected and so on;
* [`Project management documents`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/projectmanagementdocumentinfo/) - project start and end dates, number of tasks;
* [`Images`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/imagedocumentinfo/) - width, height, bits per pixel;
* [`Presentations`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/presentationdocumentinfo/) - title, author, whether it is password protected;
* [`Spreadsheets`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/spreadsheetdocumentinfo/) - title, author, worksheets count, whether it is password protected;
* [`CAD drawings`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/caddocumentinfo/) - width, height, collections of layouts and layers;
* [`Emails`](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/emaildocumentinfo/) - number and names of attachments, whether it is encrypted, whether it is signed, whether its body is in HTML format;

See the [API reference](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.contracts/) for a complete list of format-specific document metadata.

The samples below show how to obtain document info for various formats.

### PDF documents

```csharp
using (Converter converter = new Converter("sample-toc.pdf"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    PdfDocumentInfo docInfo = (PdfDocumentInfo) info;

    Console.WriteLine("Author: {0}", docInfo.Author);
    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Title: {0}", docInfo.Title);
    Console.WriteLine("Version: {0}", docInfo.Version);
    Console.WriteLine("Pages count: {0}", docInfo.PagesCount);
    Console.WriteLine("Width: {0}", docInfo.Width);
    Console.WriteLine("Height: {0}", docInfo.Height);
    Console.WriteLine("Is landscaped: {0}", docInfo.IsLandscape);
    Console.WriteLine("Is Encrypted: {0}", docInfo.IsEncrypted);
    foreach (var tocItem in docInfo.TableOfContents)
    {
        Console.WriteLine($"{tocItem.Title}: {tocItem.Page}");
    }
}
```

### Wordprocessing documents

```csharp
using (Converter converter = new Converter("sample.doc"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    WordProcessingDocumentInfo docInfo = (WordProcessingDocumentInfo) info;

    Console.WriteLine("Author: {0}", docInfo.Author);
    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Is Password Protected: {0}", docInfo.IsPasswordProtected);
    Console.WriteLine("Lines: {0}", docInfo.Lines);
    Console.WriteLine("Pages count: {0}", docInfo.PagesCount);
    Console.WriteLine("Size: {0}", docInfo.Size);
    Console.WriteLine("Title: {0}", docInfo.Title);               
    Console.WriteLine("Words: {0}", docInfo.Words);
    foreach (var tocItem in docInfo.TableOfContents)
    {
        Console.WriteLine($"{tocItem.Title}: {tocItem.Page}");
    }
}
```

### Project management documents

```csharp
using (Converter converter = new Converter("foobar.mpp"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    ProjectManagementDocumentInfo docInfo = (ProjectManagementDocumentInfo) info;

    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Start date: {0}", docInfo.StartDate);
    Console.WriteLine("End date: {0}", docInfo.EndDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Size: {0}", docInfo.Size);
    Console.WriteLine("Tasks count: {0}", docInfo.TasksCount);        
}
```

### Images

```csharp
using (Converter converter = new Converter("image.png"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    ImageDocumentInfo docInfo = (ImageDocumentInfo) info;

    Console.WriteLine("Bits per pixel: {0}", docInfo.BitsPerPixel);
    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Height: {0}", docInfo.Height);
    Console.WriteLine("Width: {0}", docInfo.Width);    
    Console.WriteLine("Size: {0}", docInfo.Size);
}
```

### Presentations

```csharp
using (Converter converter = new Converter("presentation.ppt"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    PresentationDocumentInfo docInfo = (PresentationDocumentInfo) info;

    Console.WriteLine("Author: {0}", docInfo.Author);
    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Is Password Protected: {0}", docInfo.IsPasswordProtected);    
    Console.WriteLine("Pages count: {0}", docInfo.PagesCount);
    Console.WriteLine("Size: {0}", docInfo.Size);
    Console.WriteLine("Title: {0}", docInfo.Title);               
}
```

### Spreadsheets

```csharp
using (Converter converter = new Converter("table.xlsx"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    SpreadsheetDocumentInfo docInfo = (SpreadsheetDocumentInfo) info;

    Console.WriteLine("Author: {0}", docInfo.Author);
    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Is Password Protected: {0}", docInfo.IsPasswordProtected);    
    Console.WriteLine("Pages count: {0}", docInfo.PagesCount);
    Console.WriteLine("Size: {0}", docInfo.Size);
    Console.WriteLine("Title: {0}", docInfo.Title);
    Console.WriteLine("Worksheets Count : {0}", docInfo.WorksheetsCount);
}
```
### CAD drawings

```csharp
using (Converter converter = new Converter("sample.dwg"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    CadDocumentInfo docInfo = (CadDocumentInfo) info;

    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Height: {0}", docInfo.Height);
    Console.WriteLine("Width: {0}", docInfo.Width);
    Console.WriteLine("Size: {0}", docInfo.Size);
    
    foreach (var layout in docInfo.Layouts)
    {
        Console.WriteLine($"Layout: {layout}");
    }

    foreach (var layer in docInfo.Layers)
    {
        Console.WriteLine($"Layer: {layer}");
    }
}
```

### Emails

```csharp
using (Converter converter = new Converter("sample.msg"))
{
    IDocumentInfo info = converter.GetDocumentInfo();
    EmailDocumentInfo docInfo = (EmailDocumentInfo) info;

    Console.WriteLine("Creation date: {0}", docInfo.CreationDate);
    Console.WriteLine("Format: {0}", docInfo.Format);
    Console.WriteLine("Is Encrypted: {0}", docInfo.IsEncrypted);
    Console.WriteLine("Is body in HTML: {0}", docInfo.IsHtml);
    Console.WriteLine("Is Signed: {0}", docInfo.IsSigned);
    Console.WriteLine("Size: {0}", docInfo.Size);
    Console.WriteLine("Attachments Count: {0}", docInfo.AttachmentsCount);
    foreach (var attachmentName in docInfo.AttachmentsNames)
    {
        Console.WriteLine($"Attachment Name: {attachmentName}");
    }

}
```