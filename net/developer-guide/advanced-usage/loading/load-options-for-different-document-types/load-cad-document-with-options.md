---
id: load-cad-document-with-options
url: conversion/net/load-cad-document-with-options
title: Load CAD document with options
weight: 1
description: "Learn this article and check how to load and convert CAD documents with advanced options using GroupDocs.Conversion for .NET API."
keywords: Load document, Load CAD document
productName: GroupDocs.Conversion for .NET
hideChildren: False
toc: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/net) provides [CadLoadOptions](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions) to give you control over how the source CAD document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[Format](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions/format)** | The source document type is auto-detected, but you could set the source document format explicitly with this property. Available options are: Dxf, Dwg, Dgn, Dwf, Stl, Ifc, Plt, Igs, Dwt |
|**[BackgroundColor](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions/backgroundcolor/)** | Specifies the background color for a CAD document. |
|**[DrawType](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions/drawtype/)** | Specifies the type of drawing of a CAD document. |
|**[Width](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions/width)** | Sets the desired page width |
|**[Height](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions/height)** | Sets the desired page height |
|**[LayoutNames](https://reference.groupdocs.com/conversion/net/groupdocs.conversion.options.load/cadloadoptions/layoutnames)** | Specifies which CAD layout to be converted |

### Specify layouts to be converted

The following code sample shows how to convert a CAD document and convert only certain layouts:

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

The following code sample shows how to convert a CAD document and specify the width and height:

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

### Specify background color

The following code sample shows how to convert a CAD document and specify its desired background color:

```csharp
Contracts.Func<LoadOptions> getLoadOptions = () => new CadLoadOptions
{
    BackgroundColor = System.Drawing.Color.White
};
using (Converter converter = new Converter("sample.dwg", getLoadOptions))
{
    PdfConvertOptions options = new PdfConvertOptions();
    converter.Convert("converted.pdf", options);
}
```