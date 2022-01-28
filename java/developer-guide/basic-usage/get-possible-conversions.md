---
id: get-possible-conversions
url: conversion/java/get-possible-conversions
title: Get possible conversions
weight: 1
description: "This article explains how to obtain supported conversions when convert documents with GroupDocs.Conversion within your Java applications"
keywords: 
productName: GroupDocs.Conversion for Java
hideChildren: False
---
**[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java)** allows to get possible conversions for a provided source document by following the below steps:

*   Create new instance of [Converter](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class by passing source document path as constructor's parameter
*   Call [GetPossibleConversions](https://apireference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#getPossibleConversions()) method of converter object

The following code sample demonstrates how to get possible conversions of the source document:

```java
String sourceFile = "sample.docx";
Converter converter = new Converter(sourceFile);

PossibleConversions conversions = converter.getPossibleConversions();

System.out.print(String.format("%s is of type %s and could be converted to:\n",
        Constants.SAMPLE_DOCX, conversions.getSource().getExtension()));

for (Pair<FileType, Boolean> conversion : conversions.getAll()) {
    System.out.print(String.format("\t %s as %s conversion.\n", conversion.getKey().getExtension(), conversion.getValue() ? "primary" : "secondary"));
}
```
