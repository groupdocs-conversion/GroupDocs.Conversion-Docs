---
id: load-note-document-with-options
url: conversion/net/load-note-document-with-options
title: Load Note document with options
weight: 5
description: "Learn this article and check how to load and convert Microsoft OneNote documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load Microsoft OneNote document
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [NoteLoadOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/noteloadoptions) to give you control over how source Note document will be processed. The following options could be set:

*   **[DefaultFont](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/noteloadoptions/properties/defaultfont)** - default font for Note document. The specified font will be used if a font is missing. An absolute path to font file must be provided.
*   **[FontSubstitutes](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/noteloadoptions/properties/fontsubstitutes)** - substitutes specific fonts from the Note document
*   **[Password](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/noteloadoptions/properties/password)** - password to unlock protected document

### Set Default Font

GroupDocs.Conversion for .NET allows you to set a default font name when a font is not available in the document. You can use **[DefaultFont](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/properties/defaultfont)** property of **[NoteLoadOptions](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions)** class to set the default font name. In case **[DefaultFont](https://apireference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/properties/defaultfont)** is not set the Times New Roman font will be used. The following code snippet shows how to set a default font name when converting from PDF into to wordprocessing document:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new NoteLoadOptions
{
    DefaultFont = "Helvetica"
};
using (Converter converter = new Converter("sample.one", getLoadOptions))
{
    WordProcessingConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify font substitution

The following code sample shows how to convert Note document and specify font substitution for missing fonts:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new NoteLoadOptions
{
    FontSubstitutes = new List<FontSubstitute>
    {
        FontSubstitute.Create("Tahoma", "Arial"),
        FontSubstitute.Create("Times New Roman", "Arial"),
    }
};
using (Converter converter = new Converter("sample.one", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
