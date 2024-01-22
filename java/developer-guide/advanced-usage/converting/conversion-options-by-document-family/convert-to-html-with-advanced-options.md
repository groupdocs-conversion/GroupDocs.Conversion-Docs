---
id: convert-to-html-with-advanced-options
url: conversion/java/convert-to-html-with-advanced-options
title: Convert to HTML with advanced options
weight: 1
description: "Follow this guide and learn how to convert documents to HTML format with fixed layout, zoom and other customizations using GroupDocs.Conversion for Java."
keywords: Convert to HTML, Convert HTML
productName: GroupDocs.Conversion for Java
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java)** provides the [MarkupConvertOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/MarkupConvertOptions) class to give you control over conversion results. The following options could be set:
*   [setFixedLayout](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/MarkupConvertOptions#setFixedLayout(boolean)) controls the HTML generation. If it's set to *true*, a fixed layout will be used e.g. absolutely positioned HTML element. 
*   [setZoom](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/MarkupConvertOptions#setZoom(int)) specifies the zoom level in percentage. The default value is 100.      
*   [setUsePdf](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.convert/MarkupConvertOptions#setUsePdf(boolean)). Sometimes, for better rendering and element positioning the source document should be converted to PDF first. If this property is set to *true*, the input is first converted to PDF format and after that to the desired format.  
    

The following code snippet shows how to convert to HTML with advanced options:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.MarkupConvertOptions;
import com.groupdocs.conversion.options.load.WordProcessingLoadOptions;
...
WordProcessingLoadOptions loadOptions = new WordProcessingLoadOptions();
loadOptions.setPassword("12345");

Converter converter = new Converter("sample.docx", loadOptions);
MarkupConvertOptions options = new MarkupConvertOptions();
options.setPageNumber(2);
options.setFixedLayout(true);
options.setPagesCount(1);

converter.convert("converted.html", options);
```
