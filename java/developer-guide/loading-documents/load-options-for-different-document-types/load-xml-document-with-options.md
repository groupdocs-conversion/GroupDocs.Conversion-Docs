---
id: load-xml-document-with-options
url: conversion/java/load-xml-document-with-options
title: Loading XML Documents with Options
weight: 12
description: "Learn this article and check how to load and convert XML documents with advanced options using GroupDocs.Conversion for Java API."
keywords: XML to Excel, XML to spreadsheet, XML as data source to XLSX
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
[GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) provides the [XmlLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/) class to offer fine-grained control over how XML documents are processed during conversion. This flexibility is particularly useful when working with XML data sources, applying XSL transformations, or handling external resources.
| Option | Description |
|--------|-------------|
|[**setUseAsDataSource**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#setUseAsDataSource-boolean-) | Specifies whether to treat the source XML document as a data source. |
|[**setXslFoFactory**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#setXslFoFactory-java.util.function.Supplier-com.aspose.ms.System.IO.Stream--) | Provides an XSL document stream to convert XML-FO using XSL Formatting Objects. |
|[**setXsltFactory**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/xmlloadoptions/#setXsltFactory-java.util.function.Supplier-com.aspose.ms.System.IO.Stream--) | Provides an XSLT document stream to apply XSLT transformations, typically for converting to HTML. |

These options enable you to customize the XML document loading process based on your specific requirements.

### Convert XML as a Data Source to a Spreadsheet

This example demonstrates how to use an XML document as a data source and convert it into a spreadsheet format:

{{< tabs "code-example">}}
{{< tab "XmlToSpreadsheet.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.SpreadsheetConvertOptions;
import com.groupdocs.conversion.options.load.XmlLoadOptions;

public class XmlToSpreadsheet {
    public static void convert() {
         // Load XML as a data source
        XmlLoadOptions loadOptions = new XmlLoadOptions();
        loadOptions.setUseAsDataSource(true);

        // Initialize the converter with XML and load options
        try(Converter converter = new Converter("data.xml", () -> loadOptions)) {

            // Conversion options for spreadsheet
            SpreadsheetConvertOptions options = new SpreadsheetConvertOptions();

            // Convert XML to XLSX
            converter.convert("converted.xlsx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "data.xml" >}}  
{{< tab-text >}}
`data.xml` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-xml-document-with-options/data.xml) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted.xlsx" >}}  
{{< tab-text >}}
`converted.xlsx` is converted XLSX document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-xml-document-with-options/converted.xlsx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}


## Skipping the Loading of External Resources

**External resources** refer to data or content that is linked from within an XML document but stored separately. This includes:
- Document Type Definitions (DTDs) or XML Schemas (XSDs)
- External entities
- XSLT stylesheets
- Linked images or multimedia content
- Data sources referenced in the XML

**Why Skip External Resources?**

You may want to skip loading external resources in the following cases:
- **Unavailable Resources:** When external resources are missing or inaccessible.
- **Security Concerns:** To prevent XML External Entity (XXE) attacks.
- **Performance Optimization:** To improve conversion speed by avoiding unnecessary external calls.

To learn more about skipping external resources, refer to the *[Skip Loading of External Resources](https://docs.groupdocs.com/conversion/java/skip-loading-external-resources/)* article in the [GroupDocs.Conversion](https://products.groupdocs.com/conversion/java/) documentation.