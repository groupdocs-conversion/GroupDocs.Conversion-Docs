---
id: load-document-from-url
url: conversion/nodejs-java/load-document-from-url
title: Load document from URL
weight: 3
description: "This article explains how to load PDF, Word, Excel, PowerPoint documents from URL when using GroupDocs.Conversion for Node.js via Java."
keywords: Load document from URL, Load document by URL GroupDocs.Conversion
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
The following code snippet shows how to convert a document from a URL:

```js
const fetch = require('node-fetch');

async function fetchUrl(url) {
    try {
        const response = await fetch(url);
        
        if (!response.ok) {
            throw new Error(`URL fetch error: ${response.statusText}`);
        }

        const stream = response.body;
        return stream;
    } catch (error) {
        throw new Error(error);
    }
}

const url = "https://github.com/groupdocs-conversion/GroupDocs.Conversion-for-Node.js-via-Java/blob/master/Examples/Resources/SampleFiles/sample.docx?raw=true";
try {
    const stream = await fetchUrl(url)
    const converter = new groupdocs.conversion.Converter(stream);
    const convertOptions = new groupdocs.conversion.PdfConvertOptions();
    converter.convert('converted.pdf', convertOptions);

}catch(e){
    throw new Error(e);
}
```
