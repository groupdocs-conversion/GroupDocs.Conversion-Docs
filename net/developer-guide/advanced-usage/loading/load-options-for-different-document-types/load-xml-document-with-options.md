---
id: load-xml-document-with-options
url: conversion/net/load-xml-document-with-options
title: Load XML document with options
weight: 12
description: "Learn this article and check how to load and convert XML documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: XML to Excel, XML to spreadsheet, XML as data source to XLSX
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
GroupDocs.Conversion provides [XmlLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions) to give you control over how the source XML document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[BasePath](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/basepath)** | Specifies the base path/url for the HTML |  
|**[Encoding](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/encoding)** | Specifies the encoding to be used to load the document. If not specified, the encoding will be determined from the document's character set attribute |
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/loadoptions/format)** | Input document file type |
|**[PageNumbering](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/pagenumbering)** | Whether to generate page numbers for the converted document. Default: false |
|**[ResourceLoadingTimeout](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/resourceloadingtimeout)** | Specifies the timeout of loading the external resources. |
|**[SkipExternalResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/skipexternalresources)** |  If enabled, the external resources (except for those listed in `WhitelistedResources`) will not be loaded during the conversion. |
|**[UseAsDataSource](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/useasdatasource)** | Use source XML document as a data source |
|**[WhitelistedResources](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/webloadoptions/whitelistedresources)** | Specifies which external resources will be loaded even when the loading of other external resources is restricted. |
|**[XslFoFactory](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/xslfofactory)** | XSL document stream to convert XML-FO using XSL. |
|**[XsltFactory](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/xmlloadoptions/xsltfactory/)** | XSLT document stream to convert XML performing XSL transformation to HTML. |

### Convert XML as a data source to a spreadsheet

The following code snippet shows how to use XML as a data source and convert it to a spreadsheet:

```csharp
using (Converter converter = new Converter("data.xml", (LoadContext loadContext) => new XmlLoadOptions
{
    UseAsDataSource = true
}))
{
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();
    converter.Convert("converted.xlsx", options);
}
```

### Convert XML transformed through XSLT to a PDF:

The following code shows how to convert a XML transformed through XSLT to a PDF:

```csharp
using (var converter = new Converter("books.xml", (LoadContext loadContext) => new XmlLoadOptions
   {
       XsltFactory = () => File.OpenRead("books.xsl")
   }))
{
    var options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

## Skip loading of external resources

External resources refer to data or content that is referenced or linked from within an XML document but is stored separately, typically in separate files or locations.  Common external resources include DTDs or XML schemas, entities, XSLT Stylesheets, data sources, images, multimedia, and so on. 

In some cases, you may want to skip loading all or just some of the external resources during the conversion. For example, when these resources become unavailable. Read the [Skip loading of external resources]({{< ref "conversion/net/developer-guide/advanced-usage/loading/skip-external-resources.md" >}}) article to learn how to do this with **GroupDocs.Conversion for .NET**.
