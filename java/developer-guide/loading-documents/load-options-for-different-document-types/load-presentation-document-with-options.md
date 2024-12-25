---
id: load-presentation-document-with-options
url: conversion/java/load-presentation-document-with-options
title: Load Presentation document with options
weight: 6
description: "Learn this article and check how to load and convert Microsoft PowerPoint documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load and convert PowerPoint document, Load and convert PPTX presentation, Load and convert PPT
productName: GroupDocs.Conversion for Java
hideChildren: False
---
The [GroupDocs.Conversion for Java](https://products.groupdocs.com/conversion/java/) library allows developers to load presentation files such as PPT, PPTX, and other formats into their applications with precise control over the loading process through customizable [PresentationLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions). This functionality supports advanced scenarios, including specifying slide numbers, handling hidden slides, or managing password-protected presentations.

The process involves initializing the [Converter](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion/converter/) class with the presentation file's path or stream. By defining specific properties in the [PresentationLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions), users can, for instance, load only selected slides or ensure compatibility with particular format variations. Once loaded, the document is ready for seamless conversion into any supported output format while maintaining high fidelity and preserving the source layout.

This approach is ideal for workflows involving large-scale presentation processing, batch conversions, or integrating document handling in server-side Java applications. For this the following options could be set:
| Option | Description |
|--------|-------------|
| [**setFormat()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setFormat(com.groupdocs.conversion.filetypes.PresentationFileType)) | allows you to specify explicitly the type of the source presentation document. Available options are: *Ppt, Pps, Pptx, Ppsx, Odp, Otp, Potx, Pot, Potm, Pptm, Ppsm*. |
| [**setDefaultFont()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setDefaultFont(java.lang.String)) | sets a default font for rendering the presentation. The following font will be used if a presentation font is missing. |
| [**setFontSubstitutes()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setFontSubstitutes(java.util.List))  |sets substitute specific fonts from the source presentation document. |
| [**setPassword()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setPassword(java.lang.String)) | specifies a password to unlock the protected document. |
| [**setHideComments()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setHideComments(boolean)) | specifies that comments from source presentation must be hidden during conversion. |
| [**setShowHiddenSlides()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/PresentationLoadOptions#setShowHiddenSlides(boolean)) | specifies that hidden slides should be included in the converted document. |

### Hide comments

The following code snippet shows how to convert a presentation and hide comments:

{{< tabs "code-example">}}
{{< tab "ConvertPresentationByHidingComments.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.PresentationLoadOptions;

public class ConvertPresentationByHidingComments {
    public static void convert() {
        PresentationLoadOptions loadOptions = new PresentationLoadOptions();
        loadOptions.setHideComments(true);

        try(Converter converter = new Converter("sample.pptx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_without_comments.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.pptx" >}}  
{{< tab-text >}}
`sample.pptx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-presentation-document-with-options/sample.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_without_comments.pdf" >}}  
{{< tab-text >}}
`converted_without_comments.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-presentation-document-with-options/converted_without_comments.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Specify font substitutions

The following code snippet shows how to convert a presentation and specify font substitutions for missing fonts:

{{< tabs "code-example1">}}
{{< tab "ConvertPresentationBySpecifyingFontSubstitution.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.FontSubstitute;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.PresentationLoadOptions;
import java.util.ArrayList;
import java.util.List;

public class ConvertPresentationBySpecifyingFontSubstitution {
    public static void convert() {
        PresentationLoadOptions loadOptions = new PresentationLoadOptions();

        List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
        fontSubstitutes.add(FontSubstitute.create("Tahoma", "Arial"));
        fontSubstitutes.add(FontSubstitute.create("Times New Roman", "Arial"));

        loadOptions.setFontSubstitutes(fontSubstitutes);

        try(Converter converter = new Converter("sample.pptx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_substitutes.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.pptx" >}}  
{{< tab-text >}}
`sample.pptx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-presentation-document-with-options/sample.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_substitutes.pdf" >}}  
{{< tab-text >}}
`converted_with_substitutes.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-presentation-document-with-options/converted_with_substitutes.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

### Include hidden slides

The following code snippet shows how to convert a presentation including the hidden slides:

{{< tabs "code-example2">}}
{{< tab "ConvertPresentationWithHiddenSlidesIncluded.java" >}} 
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.PresentationLoadOptions;

public class ConvertPresentationWithHiddenSlidesIncluded {
    public static void convert() {
        PresentationLoadOptions loadOptions = new PresentationLoadOptions();
        loadOptions.setShowHiddenSlides(true);

        try(Converter converter = new Converter("with_hidden_page.pptx", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_hidden_slides.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}

```
{{< /tab >}}
{{< tab "with_hidden_page.pptx" >}}  
{{< tab-text >}}
`with_hidden_page.pptx` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-presentation-document-with-options/with_hidden_page.pptx) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_hidden_slides.pdf" >}}  
{{< tab-text >}}
`converted_with_hidden_slides.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-presentation-document-with-options/converted_with_hidden_slides.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}