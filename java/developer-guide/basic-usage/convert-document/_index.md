---
id: convert-document
url: conversion/java/convert-document
title: Convert files to various formats
weight: 3
description: "This documentation explains how to convert a file to PDF, Word, Excel, PowerPoint, Email, JPG, PNG, TIFF and many other formats with just couple of lines of Java code."
keywords: Convert PDF, Convert Word, Convert Excel, Convert Email, Convert Presentation
productName: GroupDocs.Conversion for Java
hideChildren: False
structuredData:
    showOrganization: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) provides quick and easy way to convert a document to most popular formats.

Conversion to any format could be triggered by following 3 unified steps:

*   Create new instance of [**Converter**](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class and pass source document path as a constructor parameter
*   Instantiate the needed [**ConvertOptions**](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.convert/ConvertOptions) object according to your requirements.
*   Call [**Convert**](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter#convert(java.io.OutputStream,%20com.groupdocs.conversion.options.convert.ConvertOptions)) method of [**Converter**](https://apireference.groupdocs.com/conversion/java/com.groupdocs.conversion/Converter) class instance and pass name of the converted document and the instance of convert options from the previous step

Following the above 3 steps any source document you can:
