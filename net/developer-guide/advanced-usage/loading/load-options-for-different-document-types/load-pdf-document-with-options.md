---
id: load-pdf-document-with-options
url: conversion/net/load-pdf-document-with-options
title: Load PDF document with options
weight: 6
description: "Learn this article and check how to load and convert PDF documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load and convert PDF document, Load and convert EPUB document, Load and convert XPS document 
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [PdfLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions) to give you control over how the source PDF document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/format)** | The document type is auto-detected during loading, however, you can specify explicitly the type of the source document. Available options are: *Pdf, Epub, Xps, Tex, Ps, Pcl* |
|**[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/defaultfont/)** | A default font for PDF document. The specified font will be used if a font is missing. An absolute path to the font file must be provided. |
|**[FlattenAllFields](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/flattenallfields)** | Specifies that all fields in the source document should be flattened during conversion. |
|**[FontSubstitutes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/fontsubstitutes)** | Substitute specific fonts from the source document. |
|**[HidePdfAnnotations](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/hidepdfannotations)** | Specifies that annotations in the source document should be hidden. |
|**[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/password)** | A password to unlock the protected document. |
|**[RemoveEmbeddedFiles](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/removeembeddedfiles)** | Whether to remove the embedded files from the source document during the conversion. |




### Flatten all fields

The following code sample shows how to convert a PDF document and flatten all fields:

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

The following code sample shows how to convert a PDF document and hide annotations:

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

The following code sample shows how to convert a PDF document and remove embedded files:

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

### Set Default Font

GroupDocs.Conversion for .NET allows you to set a default font name when a font is not available in the document. You can use the **[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/defaultfont)** property of the **[PdfLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions)** class to set the default font name. In case the **[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/pdfloadoptions/defaultfont)** property is not set the Times New Roman font will be used. The following code snippet shows how to set a default font name when converting from PDF to word-processing document:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PdfLoadOptions
{
    DefaultFont = "Helvetica"
};
using (Converter converter = new Converter("sample.pdf", getLoadOptions))
{
    WordProcessingConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx", options);
}
```

### Specify font substitution

The following code sample shows how to convert a PDF document and specify font substitution for missing fonts:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new PdfLoadOptions
{
    FontSubstitutes = new List<FontSubstitute>
    {
        FontSubstitute.Create("Tahoma", "Arial"),
        FontSubstitute.Create("Times New Roman", "Arial"),
    }
};
using (Converter converter = new Converter("sample.pdf", getLoadOptions))
{
    PdfConvertOptions options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx", options);
}
```