---
id: load-document-from-stream
url: conversion/nodejs-java/load-document-from-stream
title: Load document from stream
weight: 2
description: "This article demonstrates how to convert document presented as stream using GroupDocs.Conversion for Node.js via Java API."
keywords: Convert document from stream, Convert file
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
There might be a case when your file is not physically located on the disk. Instead, you have the file in the form of a stream. In this case, to avoid the overhead of saving the stream as a file on disk, [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/nodejs-java) enables you to convert the file streams directly.

To load a file from a stream, follow these steps:

1.   Specify the method to obtain the file stream.
2.   Pass the method's name to the [Converter](#) class constructor.

The following code snippet serves this purpose:

```js
const fs = require('fs')
const outputPath = "LoadDocumentFromStream.pdf"

try {
  const readStream = fs.createReadStream("sample.docx")
  const stream = await groupdocs.conversion.readDataFromStream(readStream)
  const converter = new groupdocs.conversion.Converter(stream);
  const convertOptions = new groupdocs.conversion.PdfConvertOptions()

  console.log(`Source document converted successfully to ${outputPath}`)
  return converter.convert(outputPath, convertOptions)

} catch (error) {
  throw new Error(error)
}
```

The snippet above uses the [createReadStream](https://nodejs.org/api/fs.html#filehandlecreatereadstreamoptions) method. Similarly, you can use any other type of stream. Just make sure that the source stream contains any of the [supported file formats]({{< ref "conversion/nodejs-java/getting-started/supported-document-formats.md" >}}).
