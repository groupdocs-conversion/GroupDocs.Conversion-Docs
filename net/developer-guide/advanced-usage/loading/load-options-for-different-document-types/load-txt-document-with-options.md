---
id: load-txt-document-with-options
url: conversion/net/load-txt-document-with-options
title: Load TXT document with options
weight: 10
description: "Learn this article and check how to load and convert text files with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load and convert text file, Load and convert TXT
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [TxtLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/txtloadoptions) to give you control over how the source text document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[DetectNumberingWithWhitespaces](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/txtloadoptions/detectnumberingwithwhitespaces)** | Allows specifying how numbered list items are recognized when a plain-text document is converted. If this option is set to false, the lists recognition algorithm detects list paragraphs, when list numbers end with either dot, right bracket or bullet symbols (such as "•", "\*", "-" or "o"). If this option is set to true, the white spaces are also used as list number delimiters: the list recognition algorithm for Arabic style numbering (1., 1.1.2.) uses both white spaces and dot (".") symbols. |
|**[LeadingSpacesOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/txtloadoptions/leadingspacesoptions)** | Specifies how leading spaces will be processed. The available options are: *ConvertToIdent, Preserve, Trim* |
|**[TrailingSpacesOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/txtloadoptions/trailingspacesoptions)** | Specifies how trailing spaces will be processed. The available options are: *Preserve, Trim* |
|**[Encoding](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/txtloadoptions/encoding)** | Specifies the encoding to be used to load the document. |

### Control behavior of processing leading spaces

The following code sample shows how to convert a TXT document and control the way the leading spaces are processed:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new TxtLoadOptions
{
    LeadingSpacesOptions = TxtLeadingSpacesOptions.ConvertToIndent,
    DetectNumberingWithWhitespaces = true
};
using (Converter converter = new Converter("sample.txt", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Control behavior of processing trailing spaces

The following code sample shows how to convert a TXT document and the way the trailing spaces are processed:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new TxtLoadOptions
{
    TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
using (Converter converter = new Converter("sample.txt", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify encoding

The following code sample shows how to convert a TXT document and specify the encoding

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new TxtLoadOptions
{
    Encoding = Encoding.GetEncoding("shift_jis")
};
using (Converter converter = new Converter("sample.txt", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
