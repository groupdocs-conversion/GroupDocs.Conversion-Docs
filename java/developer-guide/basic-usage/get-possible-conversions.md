---
id: get-possible-conversions
url: conversion/java/get-possible-conversions
title: Get possible conversions
weight: 1
description: "This article explains how to obtain supported conversions when converting documents with GroupDocs.Conversion within your Java applications"
keywords: obtain supported conversions
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
There are multiple target formats available when converting documents with **[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java)** and you can always refer to [supported file formats]({{< ref "conversion/java/supported-document-formats.md" >}}) documentation for more details.  
But what about getting possible conversions programmatically? For example, it could allow end-users to select the target format for a specific document or to display the complete list of supported formats. 
Fortunately GroupDocs.Conversion API provides several ways to achieve this, so please check the available options below.

## Get possible conversions for a specific document

When you need to know possible conversions for a provided source document you can do this by following the below steps:

1.   Create an instance of the [Converter](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter) class by passing the source document path as the constructor's parameter.
2.   Call the [getPossibleConversions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion/Converter#getPossibleConversions()) method of the converter object.

The method will return the [PossibleConversions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.contracts/possibleconversions/) collection with a complete list of possible conversions for the source document type.

The following code snippet shows how to get possible conversions of the source document:

```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.PossibleConversions;
import com.groupdocs.conversion.contracts.Pair;
import com.groupdocs.conversion.filetypes.FileType;
...
String sourceFile = "sample.docx";
Converter converter = new Converter(sourceFile);

PossibleConversions conversions = converter.getPossibleConversions();

System.out.print(String.format("%s is of type %s and could be converted to:\n",
        sourceFile, conversions.getSource().getExtension()));

for (Pair<FileType, Boolean> conversion : conversions.getAll()) 
{
    System.out.print(String.format("\t %s as %s conversion.\n", 
        conversion.getKey().getExtension(),
        conversion.getValue() ? "primary" : "secondary"));
}
```
## Get all available conversions 

If it is required to programmatically obtain a collection of all supported conversions it is as easy as calling the [getAllPossibleConversions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/#getAllPossibleConversions--) method of the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class.

The following code snippet shows how to get all possible conversions:
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.PossibleConversions;
import com.groupdocs.conversion.contracts.TargetConversion;
...
Converter converter = new Converter();

for(PossibleConversions conversions : converter.getAllPossibleConversions())
{
    System.out.print(String.format("Source format: %s \n", conversions.getSource().getDescription() ));
    for(TargetConversion conversion : conversions.getAll())
    {
        System.out.print(String.format("\t...can be converted to %s format as %s conversion.\n",
            conversion.getFormat(),
            conversion.isPrimary()?"primary": "secondary" ));
    }
}
```