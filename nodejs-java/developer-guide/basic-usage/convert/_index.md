---
id: convert
url: conversion/nodejs-java/convert
title: Convert files to various formats
linkTitle: Convert files
weight: 3
description: "This page explains how to convert a file to PDF, Word, Excel, PowerPoint, Email, JPG, PNG, TIFF, and many other formats with just a couple of lines of JavaScript code."
keywords: Convert PDF, Convert Word, Convert Excel, Convert Email, Convert Presentation
productName: GroupDocs.Conversion for Node.js via Java
hideChildren: False
structuredData:
    showOrganization: True
---
[**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/nodejs-java) provides a quick and easy way to convert files from some source format to various ranges of target formats. The conversion process from the user's point of view is pretty simple - the source document is loaded to a converter and after conversion is completed, the result is saved to a desired file path on the local disk or other storage.

The common conversion workflow always includes the following steps:

1.   Create an instance of the **Converter** class and pass the source file path as a constructor parameter
2.   Instantiate the needed **ConvertOptions** object according to your requirements.
3.   Call the **convert** method of the **Converter** class instance and pass the name of the converted document and the instance of the conversion options from the previous step

These documentation articles explain how to convert files to the most popular formats:
