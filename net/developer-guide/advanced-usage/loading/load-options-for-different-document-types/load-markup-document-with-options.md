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
|**[BasePath](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/basepath)** | Specifies the base path/url for the HTML. |  
|**[Encoding](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/encoding)** | Specifies the encoding to be used to load the document. If not specified, the encoding will be determined from the document's character set attribute. |
|**[ExecuteScripts](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/executescripts)** | Whether the document's scripts run while it loads and converts. Default: false. Available since version 26.10. |
|**[ExternalResourceHandler](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/externalresourcehandler)** | A handler called for each resource the document asks to load; it can allow the resource, skip it or supply its content. Default: null. Available since version 26.10. |
|**[PageNumbering](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/pagenumbering)** | Whether to generate page numbers for the converted document. Default: false. |
|**[ResourceLoadingTimeout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/resourceloadingtimeout)** | Specifies the timeout of loading the external resources. |
|**[SkipExternalResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/skipexternalresources)** | Whether to skip the external resources the document references. Default: true. Content the document carries, local files inside its folder and resources that match `WhitelistedResources` still load. |
|**[WhitelistedResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/whitelistedresources)** | Absolute URI prefixes, such as `https://cdn.example.com/assets/`, of external resources to load while `SkipExternalResources` is true. Since version 26.10, an entry that is not an absolute URI prefix makes the load fail with `InvalidLoadOptionsException`. |

## Enable page numbering when converting to Word-processing formats

The following code snippet shows how to convert a markup document and insert page numbering:

```csharp
var source = "sample.html";
var loadOptions = new WebLoadOptions
{
    PageNumbering = true
};
using (var converter = new Converter(source, (LoadContext loadContext) => loadOptions))
{
    var options = new WordProcessingConvertOptions();
    converter.Convert("converted.docx" , options);
}
```

## Skip loading of external resources

External resources in the context of web documents refer to any files or data that a web page or website fetches from sources outside of its own domain or server. These external resources are essential for creating dynamic and feature-rich web experiences. Common external resources include images, audio, video, fonts, CSS, scripts, frameworks, and so on. 

External resources are not loaded by default, and scripts do not run. Read the [Skip loading of external resources]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md" >}}) article to learn how to allow trusted resources, decide per resource with a handler and run scripts with **GroupDocs.Conversion for .NET**.
