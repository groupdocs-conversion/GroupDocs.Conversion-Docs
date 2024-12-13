---
id: load-cad-document-with-options
url: conversion/java/load-cad-document-with-options
title: Load CAD document with options
weight: 1
description: "Learn this article and check how to load and convert CAD documents with advanced options using GroupDocs.Conversion for Java API."
keywords: Load document, Load CAD document
productName: GroupDocs.Conversion for Java
hideChildren: False
---

This documentation explains how to load CAD documents with configurable options using GroupDocs.Conversion for Java. It provides a flexible approach to handling and converting CAD files (such as DWG, DXF, and others) into various target formats (e.g., PDF, PNG, JPEG). Developers can customize the rendering and conversion process to suit their specific requirements using the [CadLoadOptions](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions) class. The following options can be set:
| Option | Description |
|--------|-------------|
| [**setFormat()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setFormat(com.groupdocs.conversion.filetypes.CadFileType)) | Allows you to the source document format explicitly with this property. Available options are: Dxf, Dwg, Dgn, Dwf, Stl, Ifc, Plt, Igs, Dwt. |
| [**setWidth()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setWidth(int)) | Sets the desired page width. |
| [**setHeight()**](https://reference.groupdocs.com/java/conversion/com.groupdocs.conversion.options.load/CadLoadOptions#setHeight(int)) | Sets the desired page height. |
| [**setLayoutNames()**](https://reference.groupdocs.com/conversion/java/com.groupdocs.conversion.options.load/CadLoadOptions#setLayoutNames(java.lang.String[])) | Specifies which CAD layout to be converted. |

### Specify layouts to be converted

The following code snippet shows how to convert a CAD document and convert only certain layouts:

{{< tabs "code-example">}}
{{< tab "ConvertCadAndSpecifyLayouts.java" >}}  
```java
import com.groupdocs.conversion.Converter;
import com.groupdocs.conversion.options.convert.PdfConvertOptions;
import com.groupdocs.conversion.options.load.CadLoadOptions;

public class ConvertCadAndSpecifyLayouts {
    public static void convertCadAndSpecifyLayouts() {
        CadLoadOptions loadOptions =  new CadLoadOptions();
        loadOptions.setLayoutNames(new  String[]{ "Layout1", "Layout3" });

        try(Converter converter = new Converter("with_layers_and_layouts.dwg", () -> loadOptions)) {
            PdfConvertOptions options = new PdfConvertOptions();
            converter.convert("converted_with_layout.pdf", options);
        }
    }

    public static void main(String[] args){
        convertCadAndSpecifyLayouts();
    }
}
```
{{< /tab >}}
{{< tab "with_layers_and_layouts.dwg" >}}  
{{< tab-text >}}
`with_layers_and_layouts.dwg` is sample file used in this example. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-cad-document-with-options/with_layers_and_layouts.dwg) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< tab "converted_with_layout.pdf" >}}  
{{< tab-text >}}
`converted_with_layout.pdf` is converted PDF document. Click [here](/conversion/java/_sample_files/developer-guide/loading-documents/load-cad-document-with-options/converted_with_layout.pdf) to download it.
{{< /tab-text >}}
{{< /tab >}}
{{< /tabs >}}

