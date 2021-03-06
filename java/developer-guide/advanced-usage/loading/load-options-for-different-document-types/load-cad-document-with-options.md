---
id: load-cad-document-with-options
url: conversion/java/load-cad-document-with-options
title: Load CAD document with options
weight: 1
description: "Learn this article and check how to load and convert CAD documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load CAD document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [CadLoadOptions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions) to give you control over how source CAD document will be processed. The following options could be set:

*   [**setFormat**](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setFormat(com.groupdocs.conversion.filetypes.CadFileType)) - the source document type is auto detected, but you could set the source document format explicitly with this property. Available options are: Dxf, Dwg, Dgn, Dwf, Stl, Ifc, Plt, Igs, Dwt
*   [**setWidth**](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setWidth(int)) - sets desired page width      
*   [**setHeight**](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setHeight(int)) - sets desired page height
*   [**setLayoutNames**](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/CadLoadOptions#setLayoutNames(java.lang.String[])) - specifies which CAD layout to be converted

### Specify layouts to be converted

The following code sample shows how to convert CAD document and convert only certain layouts:

```java
CadLoadOptions loadOptions =  new CadLoadOptions();
loadOptions.setLayoutNames(new  String[]{ "Layout1", "Layout3" });

Converter converter = new Converter("with_layers_and_layouts.dwg", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify width and height

The following code sample shows how to convert CAD document and specify width and height

```java
CadLoadOptions loadOptions =  new CadLoadOptions();
loadOptions.setWidth(1920);
loadOptions.setHeight(1080);

Converter converter = new Converter("with_layers_and_layouts.dwg", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
