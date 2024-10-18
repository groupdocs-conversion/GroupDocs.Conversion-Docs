---
id: load-xml-document-with-options
url: conversion/java/load-xml-document-with-options
title: Load XML document with options
weight: 12
description: "Learn this article and check how to load and convert XML documents with advanced options using GroupDocs.Conversion for Java API."
keywords: XML to Excel, XML to spreadsheet, XML as data source to XLSX
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
GroupDocs.Conversion provides [XmlLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/) to give you control over how the source XML document will be processed. The following options could be set:
| Option | Description |
|--------|-------------|
|**[setUseAsDataSource](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#isUseAsDataSource--)** | Use source XML document as a data source |
|**[setXslFoFactory](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#getXslFoFactory--)** | XSL document stream to convert XML-FO using XSL. |
|**[setXsltFactory](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#getXsltFactory--)** | XSLT document stream to convert XML performing XSL transformation to HTML. |

### Convert XML as a data source to a spreadsheet

The following code snippet shows how to use XML as a data source and convert it to a spreadsheet:

```java

    XmlLoadOptions loadOptions = new XmlLoadOptions();
    loadOptions.setUseAsDataSource(true);

    Converter converter = new Converter("data.xml", () -> loadOptions);
    SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();

    converter.convert("converted.xlsx", options);

```

### Convert XML transformed through XSLT to a PDF:

The following code shows how to convert a XML transformed through XSLT to a PDF:

```java

    XmlLoadOptions loadOptions = new XmlLoadOptions();
    loadOptions.setXslFoFactory(() -> {
        try {
            return new FileInputStream("books.xsl");
        } catch (FileNotFoundException e) {
            throw new RuntimeException(e);
        }
    });

    Converter converter = new Converter("books.xml", () -> loadOptions);
    
    PdfConvertOptions options = new PdfConvertOptions();
    converter.convert("converted.pdf", options);

```

## Skip loading of external resources

External resources refer to data or content that is referenced or linked from within an XML document but is stored separately, typically in separate files or locations.  Common external resources include DTDs or XML schemas, entities, XSLT Stylesheets, data sources, images, multimedia, and so on. 

In some cases, you may want to skip loading all or just some of the external resources during the conversion. For example, when these resources become unavailable. Read the [Skip loading of external resources]({{< ref "conversion/java/developer-guide/advanced-usage/loading/skip-external-resources.md" >}}) article to learn how to do this with [**GroupDocs.Conversion for Java**](https://products.groupdocs.com/conversion/java/).
