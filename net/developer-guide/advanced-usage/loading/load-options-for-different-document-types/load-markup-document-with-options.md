---
id: load-markup-document-with-options
url: conversion/net/load-markup-document-with-options
title: Load Markup document with options
weight: 4
description: "Learn this article and check how to load and convert HTML documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load HTML document
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
GroupDocs.Conversion provides [WebLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions) to give you control over how the source markup document will be processed. The following options could be set:
*   **[PageNumbering](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/pagenumbering)** - Whether to generate page numbers for the converted document. Default: false  

## Enable page numbering when converting to Wordprocessing

The following code sample shows how to convert a markup document and insert page numbering:


{{< alert style="info" >}}From v22.12 and greater{{< /alert >}}
```csharp
var source = "sample.html";
var loadOptions = new WebLoadOptions
{
    PageNumbering = true
};
using (var converter = new Converter(source, () => loadOptions))
{
    var options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx" , options);
}
```


{{< alert style="info" >}}Before v22.12{{< /alert >}}
```csharp
var source = "sample.html";
var loadOptions = new MarkupLoadOptions
{
    PageNumbering = true
};
using (var converter = new Converter(source, () => loadOptions))
{
    var options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx" , options);
}
```

{{< alert style="warning" >}}This functionality is introduced in v20.3{{< /alert >}}
