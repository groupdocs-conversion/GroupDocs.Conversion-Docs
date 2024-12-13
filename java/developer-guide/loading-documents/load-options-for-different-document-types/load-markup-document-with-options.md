---
id: load-markup-document-with-options
url: conversion/java/load-markup-document-with-options
title: Load Markup document with options
weight: 4
description: "Learn this article and check how to load and convert HTML documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load HTML document
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
This documentation covers the process of loading markup documents with configurable settings using [WebLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/). By leveraging these options, developers can efficiently manage markup files like HTML and MHTML, enabling accurate conversion to formats such as PDF, DOCX, or PNG. The [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) library ensures proper handling of embedded resources and document styling. The following options could be set:
| Option | Description |
|--------|-------------|
|**[setBasePath()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/#getBasePath--)** | Specifies the base path/url for the HTML. |  
|**[setEncoding()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/#getEncoding--)** | Specifies the encoding to be used to load the document. If not specified, the encoding will be determined from the document's character set attribute. |
|**[setPageNumbering()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/#isPageNumbering--)** | Whether to generate page numbers for the converted document. Default: false. |
|**[setResourceLoadingTimeout()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/#getResourceLoadingTimeout--)** | Specifies the timeout of loading the external resources. |
|**[setSkipExternalResources()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/#getSkipExternalResources--)** |  If enabled, the external resources (except for those listed in `WhitelistedResources`) will not be loaded during the conversion. |
|**[setWhitelistedResources()](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/#getWhitelistedResources--)** | Specifies which external resources will be loaded even when the loading of other external resources is restricted. |

## Enable page numbering when converting to Word-processing formats

The following code example demonstrates how to convert a markup document while adding page numbering during the conversion process.

{{< tabs "code-example">}}
{{< tab "ConvertMarkupWithAddingPageNumbering.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.WebLoadOptions;

public class ConvertMarkupWithAddingPageNumbering {
    public static void convert() {
        WebLoadOptions loadOptions =  new WebLoadOptions();
        loadOptions.setPageNumbering(true);
        loadOptions.setSkipExternalResources(true);

        try(Converter converter = new Converter("groupdocs.html", () -> loadOptions)) {
            WordProcessingConvertOptions options = new WordProcessingConvertOptions();
            converter.convert("converted_with_pagenumbering.docx", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "groupdocs.html" >}}  
{{< tab-text >}}
`groupdocs.html` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-markup-document-with-options/groupdocs.html) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_pagenumbering.docx" >}}  
{{< tab-text >}}
`converted_with_pagenumbering.docx` is converted DOCX document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-markup-document-with-options/converted_with_pagenumbering.docx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Skip loading of external resources

External resources in the context of web documents refer to any files or data that a web page or website fetches from sources outside of its own domain or server. These external resources are essential for creating dynamic and feature-rich web experiences. Common external resources include images, audio, video, fonts, CSS, scripts, frameworks, and so on. 

In some cases, you may want to skip loading all or just some of the external resources during the conversion. For example, when these resources become unavailable. Read the [Skip loading of external resources]({{< ref "conversion/java/developer-guide/loading-documents/skip-external-resources.md" >}}) article to learn how to do this with [**GroupDocs.Conversion for Java**](https://products.groupdocs.com/conversion/java/).
