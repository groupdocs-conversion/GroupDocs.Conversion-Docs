---
id: load-pdf-document-with-options
url: conversion/net/load-pdf-document-with-options
title: Load PDF document with options
weight: 6
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load and convert PDF document, Load and converi EPUB document, Load and convert XPS document 
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [PdfLoadOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/pdfloadoptions) to give you control over how source PDF document will be processed. The following options could be set:

*   **[Format](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/pdfloadoptions/properties/format)** - the document type is auto detected during loading, however you can specify explicitly the type of the source document. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl*
*   **[RemoveEmbeddedFiles](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/pdfloadoptions/properties/removeembeddedfiles)** - specifies to remove embedded files from source document during conversion
*   **[Password](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/pdfloadoptions/properties/password)** - password to unlock protected document
*   **[HidePdfAnnotations](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/pdfloadoptions/properties/hidepdfannotations)** -  specifies that annotations in the source document must be hidden
*   **[FlattenAllFields](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/pdfloadoptions/properties/flattenallfields)** - specifies that all fields in the source document will be flatten during conversion

### Flatten all fields

The following code sample shows how to convert PDF document and flatten all fields:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PdfLoadOptions
{
    FlattenAllFields = true
};
using (Converter converter = new Converter("sample.pdf", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx", options);
}
```

### Hide annotations

The following code sample shows how to convert PDF document and hide annotations:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PdfLoadOptions
{
    HidePdfAnnotations = true
};
using (Converter converter = new Converter("sample.pdf", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx", options);
}
```

### Remove embedded files

The following code sample shows how to convert PDF document and remove embedded files:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PdfLoadOptions
{
    RemoveEmbeddedFiles = true
};
using (Converter converter = new Converter("sample.pdf", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx", options);
}
```

## More resources

### Examples and Demos

Please find more [use-cases and complete C# sources]({{< ref "conversion/net/developer-guide/examples-and-demos.md" >}}) of our backend and frontend examples and try them for free!