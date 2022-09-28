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
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) supports conversion of documents that are protected with a password.

Here are the steps to follow to load and convert a password protected document:

*   Define Func<[LoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/loadoptions)\> delegate, which should return instance of document specific load options with set password
*   Create new instance of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class and pass source document path and the load options delegate as a constructor parameters
*   Instantiate the proper [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) class e.g. (**[PdfConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/pdfconvertoptions)**, **[WordProcessingConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/wordprocessingconvertoptions)**, **[SpreadsheetConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/spreadsheetconvertoptions)** etc.)
*   Call [Convert](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter/convert/#convert_3) method of [Converter](https://reference.groupdocs.com/conversion/net/groupdocs.conversion/converter) class instance and pass filename for the converted document and the instance of [ConvertOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.convert/convertoptions) from the previous step

The following code sample shows how to convert password protected document:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new WordProcessingLoadOptions
{
    Password = "12345"
};
using (Converter converter = new Converter("sample_with_password.docx", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf, options);
}
```

or can use fluent syntax

```csharp
new GroupDocs.Conversion.Converter()
    .Load("sample_with_password.docx").WithOptions(() => new WordProcessingLoadOptions
            {
                Password = "12345"
            })
    .ConvertTo("converted.pdf")
    .Convert();
```

{{< alert style="warning" >}}Fluent syntax is introduced in v22.1{{< /alert >}}
