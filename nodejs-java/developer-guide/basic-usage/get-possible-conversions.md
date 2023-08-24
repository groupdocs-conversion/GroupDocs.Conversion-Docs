---
id: get-possible-conversions
url: conversion/nodejs-java/get-possible-conversions
title: Get possible conversions
weight: 1
description: "This article explains how to obtain supported conversions when converting documents with GroupDocs.Conversion within your Java applications"
keywords: obtain supported conversions
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
toc: True
---
There are multiple target formats available when converting documents with **[GroupDocs.Conversion](https://products.groupdocs.com/conversion/nodejs-java)** and you can always refer to [supported file formats]({{< ref "conversion/nodejs-java/getting-started/supported-document-formats.md" >}}) documentation for more details.  
But what about getting possible conversions programmatically? For example, it could allow end-users to select the target format for a specific document or to display the complete list of supported formats. 
Fortunately GroupDocs.Conversion API provides several ways to achieve this, so please check the available options below.

## Get possible conversions for a specific document

When you need to know possible conversions for a provided source document you can do this by following the below steps:

*   Create a new instance of the [Converter](#) class by passing the source document path as the constructor's parameter.
*   Call the [getPossibleConversions](#) method of the converter object.

The method will return the [PossibleConversions](#) collection with a complete list of possible conversions for the source document type.

The following code sample demonstrates how to get possible conversions of the source document:

```js
const sourceFile = "sample.docx";
const converter = new groupdocs.conversion.Converter(sourceFile);
const conversions = converter.getPossibleConversions();
console.log(
  util.format(
    '%s is of type %s and could be converted to:\n',
    inputFilePath,
    conversions.getSource().getExtension()
  )
);

const items = conversions.getAll();
console.log(items);

items.spliterator().getExactSizeIfKnown();

for (let i = 0; i < items.size(); i += 1) {
  const item = items.get(i);
  console.log(
    `\t ${item.getFormat().getExtension()} as ${
      item.isPrimary() ? 'primary' : 'secondary'
    } conversion.\n`
  );
}
```
## Get all available conversions 

If it is required to programmatically obtain a collection of all supported conversions it is as easy as calling the [getAllPossibleConversions](#) method of the [Converter](#) class.

The following code sample demonstrates how to get all possible conversions:

```js
const sourceFile = "sample.docx";
const converter = new groupdocs.conversion.Converter(sourceFile);
const conversions = converter.getPossibleConversions();
console.log(
  util.format(
    'Source format: %s \n',
    conversions.getSource().getDescription()
  )
);

const items = conversions.getAll();
items.spliterator().getExactSizeIfKnown();

for (let i = 0; i < items.size(); i += 1) {
  const item = items.get(i)
  console.log(util.format('\t...can be converted to %s format as %s conversion.\n'), item.getFormat(),  item.isPrimary() ? 'primary' : 'secondary');
}
```