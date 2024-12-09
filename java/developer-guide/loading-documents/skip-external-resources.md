---
id: skip-loading-external-resources
url: conversion/java/skip-loading-external-resources
title: Skip loading of external resources
weight: 4
description: "Learn this article and check how to restrict loading of external resources during conversion"
keywords: Restrict loading of external resources during conversion, external resources, Skip loading of external resources during conversion, Loading external resources
productName: GroupDocs.Conversion for Java
hideChildren: False
toc: True
---
## What are external resources?
*External resources* refer to various types of content or files that are not directly embedded within the document but are instead referenced and loaded from external locations. These resources enhance the functionality, appearance, and interactivity of the document. Common external resources include images, audio, video, fonts, CSS, scripts, frameworks, and so on. **GroupDocs.Conversion** considers external any resource that a document is trying to load from an external URL.

Utilizing external resources optimizes the performance, maintainability, and scalability of web pages and other documents. These resources are typically cached by browsers, which can reduce the load time of subsequent visits to a website. However, relying too heavily on external resources can also introduce dependencies and potential points of failure if the external sources become unavailable.

## Restricting all external resources
While loading [web]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-markup-document-with-options.md" >}}), [presentations]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-presentation-document-with-options.md" >}}) and [word-processing]({{< ref "conversion/java/developer-guide/loading-documents/load-options-for-different-document-types/load-wordprocessing-document-with-options.md" >}}) documents, the [**GroupDocs.Conversion**](https://products.groupdocs.com/conversion/java) allows skipping of loading the external resources.

To restrict the loading of external resources during the conversion, use the `getSkipExternalResources()` boolean property of the respective [WebLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/), [PresentationLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/presentationloadoptions/), or [WordProcessingLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/wordprocessingloadoptions/) class.

The following code snippet shows how to skip loading of external resources while loading an HTML document:

{{< tabs "code-example1">}}
{{< tab "skip_external_resources.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WebLoadOptions;

public static void skipExternalResources()
{
    String outputFile = "skip_external_resources.pdf";

    WebLoadOptions loadOptions =  new WebLoadOptions();
    loadOptions.setSkipExternalResources(true);

    Converter converter = new Converter("groupdocs.html", ()-> loadOptions);

    PdfConvertOptions options = new PdfConvertOptions();
    converter.convert(outputFile, options);
}

public static void main(String[] args){
    skipExternalResources();
}
```
{{< /tab >}}
{{< tab "groupdocs.html" >}}  
{{< tab-text >}}
`groupdocs.html` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/skip-loading-external-resources/groupdocs.html) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "skip_external_resources.pdf" >}}  
{{< tab-text >}}
`skip_external_resources.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/skip-loading-external-resources/skip_external_resources.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

## Allowlisting some of the external resources
Sometimes you may want to skip loading most of the external resources, but still load some particular resources.
To allow-list specific resources during the conversion, use the `WhitelistedResources` property of the respective [WebLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/webloadoptions/), [PresentationLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/presentationloadoptions/), or [WordProcessingLoadOptions](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/wordprocessingloadoptions/) class. The property is effective when the `SkipExternalResources` property is enabled. The `WhitelistedResources` property accepts the string list containing the portions of URLs to be loaded while restricting the loading of other external resources. 

The following code snippet shows how to load the JPG and JPEG images and any resources from the `example.com` domain while restricting any other external resources:

{{< tabs "code-example2">}}
{{< tab "whitelisted_resources.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.WebLoadOptions;

public static void setWhitelistedResources()
{
    String outputFile = "whitelisted_resources.pdf";

    WebLoadOptions loadOptions =  new WebLoadOptions();
    loadOptions.setSkipExternalResources(true);
    loadOptions.setWhitelistedResources(Arrays.asList( "jpeg", "via.placeholder.com" ));

    Converter converter = new Converter("groupdocs.html", ()-> loadOptions);

    PdfConvertOptions options = new PdfConvertOptions();
    converter.convert(outputFile, options);
}

public static void main(String[] args){
    setWhitelistedResources();
}
```
{{< /tab >}}
{{< tab "groupdocs.html" >}}  
{{< tab-text >}}
`groupdocs.html` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/skip-loading-external-resources/groupdocs.html) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "whitelisted_resources.pdf" >}}  
{{< tab-text >}}
`whitelisted_resources.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/skip-loading-external-resources/whitelisted_resources.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}