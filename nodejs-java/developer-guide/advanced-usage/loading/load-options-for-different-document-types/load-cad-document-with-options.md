---
id: load-cad-document-with-options
url: conversion/nodejs-java/load-cad-document-with-options
title: Load CAD document with options
weight: 1
description: "Learn this article and check how to load and convert CAD documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load CAD document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [CadLoadOptions](#) to give you control over how the source CAD document will be processed. The following options could be set:

*   [**setFormat**](#) - the source document type is auto-detected, but you could set the source document format explicitly with this property. Available options are: Dxf, Dwg, Dgn, Dwf, Stl, Ifc, Plt, Igs, Dwt
*   [**setWidth**](#) - sets the desired page width      
*   [**setHeight**](#) - sets the desired page height
*   [**setLayoutNames**](#) - specifies which CAD layout to be converted

### Specify layouts to be converted

The following code sample shows how to convert a CAD document and convert only certain layouts:

```js
const outputPath = "ConvertCadAndSpecifyLayouts.pdf"
  
const loadOptions = new groupdocs.conversion.CadLoadOptions()
loadOptions.setLayoutNames(["Layout1", "Layout3"]);
const converter = new groupdocs.conversion.Converter("with_layers_and_layouts.dwg", () => loadOptions);

const convertOptions = new groupdocs.conversion.PdfConvertOptions()
console.log(`Cad document converted successfully to ${outputPath} (cad & specify layouts)`)
converter.convert(outputPath, convertOptions)
```

### Specify width and height

The following code sample shows how to convert a CAD document and specify the width and height

```js
const outputPath = "convertCadAndSpecifyWidthAndHeight.tiff"

const loadOptions = new groupdocs.conversion.CadLoadOptions()
loadOptions.setWidth(1920);
loadOptions.setHeight(1080);

const converter = new groupdocs.conversion.Converter("with_layers_and_layouts.dwg", () => loadOptions);

const convertOptions = new groupdocs.conversion.ImageConvertOptions();
convertOptions.setFormat_ConvertOptions_New(groupdocs.conversion.ImageFileType.Tiff);

console.log(`Cad document converted successfully to ${outputPath} (cad & specify width and height)`)
converter.convert(outputPath, convertOptions)
```
