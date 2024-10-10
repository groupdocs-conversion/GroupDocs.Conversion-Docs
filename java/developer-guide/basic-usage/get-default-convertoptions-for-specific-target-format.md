---
id: get-default-convertoptions-for-specific-target-format
url: conversion/java/get-default-convertoptions-for-specific-target-format
title: Get default ConvertOptions for specific target format
weight: 4
description: "Learn this article and check how to obtain default convert options for specific conversion format with GroupDocs.Conversion for Java API. "
keywords: Convert settings, Convert options, Convert with GroupDocs.Conversion
productName: GroupDocs.Conversion for Java
hideChildren: False
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) allows to get default convert options for specific target format by following the below steps:

1.   Create new instance of [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class by passing source document path as constructor's parameter
2.   Call [GetPossibleConversions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#getPossibleConversions--) method of converter object
3.   Use the file extension or `FileType` as key to indexer of object received as value in previous step  

The following code snippet shows how to get possible conversions of the source document:

```java
Converter converter = new Converter("source.docx");

PossibleConversions conversions = converter.getPossibleConversions();
TargetConversion targetConversion = conversions.getTargetConversion("pdf");
ConvertOptions convertOptions = targetConversion.getConvertOptions();
if (convertOptions != null)
{
    converter.convert("converted.pdf", convertOptions);
}

```
