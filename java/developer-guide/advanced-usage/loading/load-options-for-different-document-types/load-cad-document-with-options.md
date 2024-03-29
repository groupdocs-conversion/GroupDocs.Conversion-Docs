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
GroupDocs.Conversion provides the [CadLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions) class to give you control over how the source CAD document will be processed. The following options could be set:

*   [**setFormat**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setFormat(com.groupdocs.conversion.filetypes.CadFileType)) allows you to the source document format explicitly with this property. Available options are: Dxf, Dwg, Dgn, Dwf, Stl, Ifc, Plt, Igs, Dwt.
*   [**setWidth**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setWidth(int)) sets the desired page width.    
*   [**setHeight**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setHeight(int)) sets the desired page height.
*   [**setLayoutNames**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/CadLoadOptions#setLayoutNames(java.lang.String[])) specifies which CAD layout to be converted.

### Specify layouts to be converted

The following code snippet shows how to convert a CAD document and convert only certain layouts:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CadLoadOptions;
...
CadLoadOptions loadOptions =  new CadLoadOptions();
loadOptions.setLayoutNames(new  String[]{ "Layout1", "Layout3" });

Converter converter = new Converter("with_layers_and_layouts.dwg", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```

### Specify width and height

The following code snippet shows how to convert a CAD document and specify the width and height:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.load.CadLoadOptions;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
...
CadLoadOptions loadOptions =  new CadLoadOptions();
loadOptions.setWidth(1920);
loadOptions.setHeight(1080);

Converter converter = new Converter("with_layers_and_layouts.dwg", loadOptions);
PdfConvertOptions options = new PdfConvertOptions();
converter.convert("converted.pdf", options);
```
