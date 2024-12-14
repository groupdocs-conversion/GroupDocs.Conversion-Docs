---
id: load-note-document-with-options
url: conversion/java/load-note-document-with-options
title: Load Note document with options
weight: 4
description: "Learn this article and check how to load and convert Microsoft OneNote documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load Microsoft OneNote document
productName: GroupDocs.Conversion for Java
hideChildren: False
---
This documentation explains how to load Note documents, such as OneNote files, using GroupDocs.Conversion for Java with [NoteLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions) class. The API allows developers to specify parameters for processing Note documents, including page ranges and rendering settings, enabling precise control over conversion to formats like PDF, PNG, or DOCX. The following options could be set:
| Option | Description |
|--------|-------------|
| [**setDefaultFont()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions#setDefaultFont(java.lang.String)) | Specifies a default font for Note document. The specified font will be used if a font is missing. |
| [**setFontSubstitutes()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions#setFontSubstitutes(java.util.List)) | Specifies substitutes specific fonts from the Note document. |
| [**setPassword()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/NoteLoadOptions#setPassword(java.lang.String)) | Specifies a password to unlock the protected document. |

### Specify font substitution

The following code snippet shows how to convert a Note document and specify font substitution for missing fonts:

{{< tabs "code-example">}}
{{< tab "ConvertNoteBySpecifyingFontSubstitution.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.contracts.FontSubstitute;
import com.groupdocs.conversion.options.convert.WordProcessingConvertOptions;
import com.groupdocs.conversion.options.load.NoteLoadOptions;
import java.util.ArrayList;
import java.util.List;

public class ConvertNoteBySpecifyingFontSubstitution {
    public static void convert() {
        NoteLoadOptions loadOptions =  new NoteLoadOptions();

        List<FontSubstitute> fontSubstitutes = new ArrayList<FontSubstitute>();
        fontSubstitutes.add(FontSubstitute.create("Calibri", "Arial"));
        fontSubstitutes.add(FontSubstitute.create("Times New Roman", "Arial"));

        loadOptions.setFontSubstitutes(fontSubstitutes);

        try(Converter converter = new Converter("sample.one", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_font_substitution.pdf", options);
        }
    }

    public static void main(String[] args){
        convert();
    }
}
```
{{< /tab >}}
{{< tab "sample.one" >}}  
{{< tab-text >}}
`sample.one` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-note-document-with-options/sample.one) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_font_substitution.pdf" >}}  
{{< tab-text >}}
`converted_with_font_substitution.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-note-document-with-options/converted_with_font_substitution.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}