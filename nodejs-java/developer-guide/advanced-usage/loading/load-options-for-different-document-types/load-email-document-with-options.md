---
id: load-email-document-with-options
url: conversion/nodejs-java/load-email-document-with-options
title: Load Email document with options
weight: 3
description: "Learn this article and check how to load and convert Email documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load Email document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
GroupDocs.Conversion provides [EmailLoadOptions](#) to give you control over how the source email document will be processed. The following options could be set:

*   **[**set**Format](#)** specifies the document type is auto-detected during loading, however, you can specify explicitly the type of the source email document. Available options are: Msg, Eml, Emlx, Pst, Ost, Vcf, Mht. 
*   **[**setD**isplayHeader](#)** specifies option to display or hide the email header.     
*   **[**setD**isplayFromEmailAddress](#)** specifies option to display or hide "from" email address.
*   **[**setD**isplayEmailAddress](#)** specifies option to display or hide email address
*   **[**setD**isplayToEmailAddress](#)** specifies option to display or hide "to" email address.
*   **[**setD**isplayCcEmailAddress](#)** specifies option to display or hide "Cc" email address.
*   **[setDisplayBccEmailAddress](#)** specifies  option to display or hide "Bcc" email address.

### Control fields visibility

The following code snippet shows how to convert an Email document and control the visibility of the fields:

```js
const outputPath = "ConvertEmailWithAlteringFieldsVisibility.pdf"

const loadOptions = new groupdocs.conversion.EmailLoadOptions();
loadOptions.setDisplayHeader(false);
loadOptions.setDisplayFromEmailAddress(false);
loadOptions.setDisplayToEmailAddress(false);
loadOptions.setDisplayEmailAddress(false);
loadOptions.setDisplayCcEmailAddress(false);
loadOptions.setDisplayBccEmailAddress(false);
loadOptions.setConvertOwned(false);

const converter = new groupdocs.conversion.Converter("sample.msg", loadOptions)
const convertOptions = new groupdocs.conversion.PdfConvertOptions()

console.log(`Email document converted successfully to ${outputPath} (with altering fields visibility)`)
converter.convert(outputPath, convertOptions)
```
