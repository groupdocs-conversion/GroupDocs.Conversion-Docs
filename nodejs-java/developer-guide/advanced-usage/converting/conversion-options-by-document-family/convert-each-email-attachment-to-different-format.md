---
id: convert-each-email-attachment-to-different-format
url: conversion/nodejs-java/convert-each-email-attachment-to-different-format
title: Convert each email attachment to different format
weight: 2
description: "Follow this guide and learn how to convert email attachments to different format based on attachment type using GroupDocs.Conversion for Node.js via Java."
keywords: Convert email attachments, Convert MSG attachments, Convert EML attachments
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
---
GroupDocs.Conversion provides a flexible API to control the conversion of documents that contain other documents. The following code snippet shows how to convert each attachment to a different format based on attachment type:

```js
const fs = require('fs').promises;

const emailLoadOptions = new groupdocs.conversion.EmailLoadOptions();
emailLoadOptions.setConvertOwned(true);
emailLoadOptions.setConvertOwner(true);
emailLoadOptions.setDepth(2);

const converter = new groupdocs.conversion.Converter("sample_with_attachments.eml", emailLoadOptions);

const convertOptions = new groupdocs.conversion.PdfConvertOptions();

convertOptions.setPassword("12345");
convertOptions.setDpi(300);

const fileOutputStreams = [];
try{
    await converter.convert(async (t) => {
        try {
            const fileOutputStream = await fs.open(`converted-${fileOutputStreams.length}.pdf`, 'w');
            fileOutputStreams.push(fileOutputStream);
            return fileOutputStream;
        } catch (e) {
            throw new Error(e);
        }
    }, options);
} finally {
    try {
        for (const fileOutputStream of fileOutputStreams) {
            await fileOutputStream.close();
        }
    } catch (e) {
        // throw an exception
    }
}
```

{{< alert style="warning" >}}This functionality is introduced in v21.7{{< /alert >}}
