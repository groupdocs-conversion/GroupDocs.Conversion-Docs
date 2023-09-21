---
id: load-markup-document-with-options
url: conversion/net/load-markup-document-with-options
title: Load Markup document with options
weight: 4
description: "Learn this article and check how to load and convert HTML documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load HTML document
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides [WebLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions) to give you control over how the source markup document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[BasePath](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/basepath)** | Specifies the base path/url for the HTML |  
|**[Encoding](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/encoding)** | Specifies the encoding to be used to load the document. If not specified, the encoding will be determined from the document's character set attribute |
|**[PageNumbering](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/pagenumbering)** | Whether to generate page numbers for the converted document. Default: false |
|**[ResourceLoadingTimeout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/resourceloadingtimeout)** | Specifies the timeout of loading the external resources. |
|**[SkipExternalResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/skipexternalresources)** |  If enabled, the external resources (except for those listed in `WhitelistedResources`) will not be loaded during the conversion. |
|**[WhitelistedResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/whitelistedresources)** | Specifies which external resources will be loaded even when the loading of other external resources is restricted. |

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

## Skip loading of external resources
External resources in the context of web documents refer to any files or data that a web page or website fetches from sources outside of its own domain or server. These external resources are essential for creating dynamic and feature-rich web experiences. Common external resources include images, audio, video, fonts, CSS, scripts, frameworks, and so on. 

In some cases, you may want to skip loading all or just some of the external resources during the conversion. For example, when these resources become unavailable. Read the [Skip loading of external resources]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md" >}}) article to learn how to do this with **GroupDocs.Conversion for .NET** 
