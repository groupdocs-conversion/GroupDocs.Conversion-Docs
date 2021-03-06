---
id: load-cad-document-with-options
url: conversion/net/load-cad-document-with-options
title: Load CAD document with options
weight: 1
description: "Learn this article and check how to load and convert CAD documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load CAD document
productName: GroupDocs.Conversion for .NET
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [CadLoadOptions](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/cadloadoptions) to give you control over how source CAD document will be processed. The following options could be set:

*   **[Format](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/cadloadoptions/properties/format)** - the source document type is auto detected, but you could set the source document format explicitly with this property. Available options are: Dxf, Dwg, Dgn, Dwf, Stl, Ifc, Plt, Igs, Dwt
*   **[Width](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/cadloadoptions/properties/width)** - sets desired page width 
*   **[Height](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/cadloadoptions/properties/height)** - sets desired page height
*   **[LayoutNames](https://apireference.groupdocs.com/net/conversion/groupdocs.conversion.options.load/cadloadoptions/properties/layoutnames)** - specifies which CAD layout to be converted

### Specify layouts to be converted

The following code sample shows how to convert cad document and convert only certain layouts:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CadLoadOptions
{
    LayoutNames = new []{ "Layout1", "Layout3" }
};
using (Converter converter = new Converter("with_layers_and_layouts.dwg", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```

### Specify width and height

The following code sample shows how to convert cad document and specify width and height

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CadLoadOptions
{
    Width = 1920,
    Height = 1080
};
using (Converter converter = new Converter("with_layers_and_layouts.dwg", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```
