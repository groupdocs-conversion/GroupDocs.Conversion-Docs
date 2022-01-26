---
id: load-csv-document-with-options
url: conversion/net/load-csv-document-with-options
title: Load CSV document with options
weight: 2
description: "Learn this article and check how to load and convert CSV documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load CSV document
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [CsvLoadOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions) to give you control over how source CSV document will be processed. The following options could be set:

*   **[Separator](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions/properties/separator)** - specifies the delimiter 
*   **[IsMultiEncoded](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions/properties/ismultiencoded)** - if *true*, means that the document contains several encodings  
*   **[HasFormula](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions/properties/hasformula)** - specifies that if text starts with "=" it should be parsed as a formula
*   **[ConvertNumericData](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions/properties/convertnumericdata)** - specifies that strings with digits should be parsed as numbers
*   **[ConvertDateTimeData](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions/properties/convertdatetimedata)** - specifies that date/time string should be detected and parsed to DateTime
*   **[Encoding](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/csvloadoptions/properties/encoding)** - specifies the encoding to be used during load

### Control behavior of converting date/time and numeric data

The following code sample shows how to convert csv document and control the way the date/time and numeric data have been processed:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    ConvertDateTimeData = true,
    ConvertNumericData = true
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify delimiter

The following code sample shows how to convert csv document and specify the delimiter

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    Separator = ','
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify encoding

The following code sample shows how to convert csv document and specify the encoding

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CsvLoadOptions
{
    Encoding = Encoding.GetEncoding("shift_jis")
};
using (Converter converter = new Converter("sample.csv", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
