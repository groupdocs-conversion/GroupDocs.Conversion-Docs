---
id: convert-txt
url: conversion/net/convert/txt
title: Convert TXT
weight: 1
description: "Learn this documentation and check how to convert files from/to text format with GroupDocs.Conversion for .NET."
keywords: Convert to text, Convert to TXT, Convert text file
productName: GroupDocs.Conversion for .NET
hideChildren: False
showAllChildrenTable: True
---

## About TEXT File Format

A file with .TXT extension represents a text document that contains plain text in the form of lines. Paragraphs in a text document are recognized by carriage returns and are used for better arrangement of file contents. A standard text document can be opened in any text editor or word processing application on different operating systems. All the text contained in such a file is in human-readable format and represented by sequence of characters.

### Convert from TEXT

With [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net) you can easily convert your TEXT document into another file format.  
For example TEXT to PDF conversion code snippet will look like this:

```csharp
// Load the source TXT file
using (var converter = new GroupDocs.Conversion.Converter("sample.txt"))
{
    // Set the convert options for PDF format
   var options = new PdfConvertOptions();
    // Convert to PDF format
    converter.Convert("converted.pdf", options);
}
```

Put it simply - you just load a TEXT file into `Converter`, select desired output format and all the rest will be done by **GroupDocs.Conversion**.  

{{< alert style="info" >}}
For more available conversions and formats compatibility check [supported file formats]({{< ref "conversion/net/getting-started/supported-document-formats.md" >}}).
Refer to [API reference](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert) for more conversion options and customizations.
{{< /alert >}}

### Convert to TEXT

On the other hand, converting your files to TEXT format is also quite simple and natural.
The following code sample demonstrates how to convert PDF document to TEXT in C# using [GroupDocs.Conversion](https://products.groupdocs.com/conversion/net).

```csharp
// Load the source PDF file
using (var converter = new GroupDocs.Conversion.Converter("sample.pdf"))
{
    // Set the convert options for TXT format
   WordProcessingConvertOptions options = new WordProcessingConvertOptions { Format = GroupDocs.Conversion.FileTypes.WordProcessingFileType.Txt };
    // Convert to TXT format
    converter.Convert("converted.txt", options);
}
```

For more detailed code examples of how to convert various file formats to TEXT please check articles provided below.
