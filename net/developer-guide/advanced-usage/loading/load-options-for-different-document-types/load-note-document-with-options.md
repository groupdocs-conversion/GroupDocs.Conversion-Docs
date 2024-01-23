---
id: load-note-document-with-options
url: conversion/net/load-note-document-with-options
title: Load Note document with options
weight: 5
description: "Learn this article and check how to load and convert Microsoft OneNote documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load Microsoft OneNote document
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [NoteLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions) to give you control over how the source Note document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/defaultfont)** | A default font for Note document. The specified font will be used if a font is missing. An absolute path to the font file must be provided. |
|**[FontSubstitutes](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/fontsubstitutes)** | Substitutes specific fonts from the Note document. |
|**[Password](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/password)** | A password to unlock the protected document. |

### Set Default Font

GroupDocs.Conversion for .NET allows you to set a default font name when a font is not available in the document. You can use **[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/defaultfont)** property of **[NoteLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions)** class to set the default font name. In case **[DefaultFont](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/noteloadoptions/defaultfont)** is not set the Times New Roman font will be used. The following code snippet shows how to set a default font name when converting from PDF into to Word processing document:

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

The following code snippet shows how to convert Note document and specify font substitution for missing fonts:

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
