---
id: load-password-protected-document
url: conversion/net/load-password-protected-document
title: Load password-protected document
weight: 4
description: "Learn this article and check how to load and convert password-protected documents using GroupDocs.Conversion for .NET API."
keywords: Load and convert password-protected document, convert protected document, Load and convert document with password, convert document with password
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) supports the conversion of documents that are protected with a password.

To load and convert a password-protected document, follow these steps:

1.   Define a Func<[LoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/loadoptions)\> delegate, which should return an instance of document-specific load options with the password specified.
2.   Create an instance of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass the source document path and the load options delegate as the constructor parameters.
3.   Instantiate the appropriate [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)**, etc.)
4.   Call the [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of the [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass the filename for the converted document and the instance of the [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous step.

The following code snippet shows how to convert password protected document:

```csharp
Func<LoadContext, LoadOptions> getLoadOptions = loadContext => new WordProcessingLoadOptions
{
    Password = "12345"
};
using (Converter converter = new Converter("sample_with_password.docx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

You can also use [fluent syntax]({{< ref "conversion/net/developer-guide/basic-usage/fluent-syntax.md" >}}):

```csharp
FluentConverter
    .Load("sample_with_password.docx").WithOptions((LoadContext loadContext) => new WordProcessingLoadOptions
    {
        Password = "12345"
    })
    .ConvertTo("converted.pdf")
    .Convert();
```
